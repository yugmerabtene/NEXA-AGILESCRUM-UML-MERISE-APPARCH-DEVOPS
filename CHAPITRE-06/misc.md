1. 👉 Une **application Java Spring Boot** qui fait une addition
2. ✅ Un **test unitaire**
3. 🐳 Un **build Docker**
4. 🚀 Un **déploiement automatique** sur une VM sous Proxmox via SSH

---

## 🔧 1. Architecture globale

```
[ Poste Dev ] → push →
[ VM GitLab + Runner Docker ] → CI/CD
 → Test → Build Docker → SSH Deploy
                             ↓
                    [ VM cible sous Proxmox ]
```

---

## 📁 2. Structure du projet

```
spring-addition/
├── .gitlab-ci.yml
├── Dockerfile
├── pom.xml
└── src/
    ├── main/
    │   └── java/com/example/demo/
    │       └── AdditionController.java
    └── test/
        └── java/com/example/demo/
            └── AdditionTest.java
```

---

## 🧠 3. Code Java Spring Boot

### `AdditionController.java`

```java
package com.example.demo;

import org.springframework.web.bind.annotation.*;

@RestController
public class AdditionController {
    @GetMapping("/add")
    public int add(@RequestParam int a, @RequestParam int b) {
        return a + b;
    }
}
```

---

## ✅ 4. Test unitaire

### `AdditionTest.java`

```java
package com.example.demo;

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class AdditionTest {
    @Test
    public void testAddition() {
        AdditionController controller = new AdditionController();
        assertEquals(5, controller.add(2, 3));
    }
}
```

---

## ⚙️ 5. Fichier `pom.xml` (extrait minimal)

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" ...>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>spring-addition</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>jar</packaging>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>
```

---

## 🐳 6. Dockerfile

```dockerfile
FROM openjdk:17
WORKDIR /app
COPY target/spring-addition-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
```

---

## 🧪 7. `.gitlab-ci.yml`

```yaml
stages:
  - test
  - build
  - dockerize
  - deploy

variables:
  APP_NAME: spring-addition
  TARGET_HOST: vm-user@VM-IP
  TARGET_PATH: /opt/apps

test:
  stage: test
  script:
    - ./mvnw test

build:
  stage: build
  script:
    - ./mvnw clean package -DskipTests

dockerize:
  stage: dockerize
  image: docker:latest
  services:
    - docker:dind
  script:
    - docker build -t $APP_NAME .
    - docker save $APP_NAME | gzip > $APP_NAME.tar.gz

deploy:
  stage: deploy
  script:
    - echo "$SSH_PRIVATE_KEY" > key.pem && chmod 600 key.pem
    - scp -i key.pem $APP_NAME.tar.gz $TARGET_HOST:/tmp/
    - ssh -i key.pem $TARGET_HOST "
        docker load < /tmp/$APP_NAME.tar.gz &&
        docker stop $APP_NAME || true &&
        docker rm $APP_NAME || true &&
        docker run -d --name $APP_NAME -p 8080:8080 $APP_NAME"
```

---

## 🔐 8. Clé SSH et GitLab

1. Sur le runner :

   ```bash
   ssh-keygen -t rsa -b 4096
   ```

2. Ajoute la **clé publique** dans `~/.ssh/authorized_keys` de ta VM cible

3. Dans GitLab :

   * Va dans ton repo → `Settings > CI/CD > Variables`
   * Ajoute une variable :

     * `Key`: `SSH_PRIVATE_KEY`
     * `Value`: contenu de ta **clé privée**

---

## 🧪 9. Exécution du pipeline

1. Tu pushes ton code sur GitLab
2. GitLab :

   * ✅ Lance les tests
   * 🔨 Build avec Maven
   * 🐳 Build l'image Docker
   * 📤 Transfère le `.tar.gz` sur la VM
   * 🚀 Déploie et redémarre le conteneur
