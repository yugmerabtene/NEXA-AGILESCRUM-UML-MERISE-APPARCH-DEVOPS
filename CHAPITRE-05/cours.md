# 🎓 CHAPITRE-05 – Tests logiciels, couverture et automatisation

## 🎯 Objectifs pédagogiques

* Comprendre les enjeux et les différents types de tests logiciels
* Apprendre à écrire et maintenir des **tests unitaires efficaces**
* Mettre en œuvre des **tests d’intégration**, de **sécurité** et de **non-régression**
* Utiliser des **frameworks de tests** et outils de **couverture**
* Intégrer les tests dans une **chaîne CI/CD**

---

## 1. 🧠 Introduction au test logiciel

### Pourquoi tester ?

* Garantir la qualité du code
* Éviter les régressions
* Automatiser la vérification du bon fonctionnement
* Renforcer la documentation via des cas concrets

### Les différents types de tests :

| Type de test          | Portée                          | Objectif principal                                 |
| --------------------- | ------------------------------- | -------------------------------------------------- |
| 🧪 **Unitaire**       | Fonction ou méthode             | Valider un comportement précis et isolé            |
| 🔗 **Intégration**    | Plusieurs modules liés          | Vérifier la communication entre composants         |
| 🎯 **Fonctionnel**    | Cas métier complets             | Valider les exigences fonctionnelles               |
| 🧭 **E2E**            | Parcours utilisateur complet    | Simuler le comportement d’un utilisateur           |
| 🔐 **Sécurité**       | Points critiques (auth, droits) | Identifier les failles (XSS, injection, etc.)      |
| 🔁 **Non-régression** | Tout le périmètre               | Assurer qu’une nouvelle modification ne casse rien |

### Stratégies de test :

* **TDD (Test Driven Development)** : écrire le test avant le code
* **BDD (Behavior Driven Development)** : focalisation sur les comportements métier

---

## 2. 🧪 Les tests unitaires

### Définition :

Tester **une unité de code isolée** : méthode, fonction ou composant, **sans dépendance externe**.

### Ce qu'on teste :

* Résultat attendu pour des entrées précises
* Comportement en cas d’entrée invalide
* Exceptions et erreurs

### Ce qu'on NE teste PAS :

* Connexion à une base de données
* Appels à des services externes
* Intégration entre modules

### Structure d’un test : **GIVEN / WHEN / THEN**

```java
@Test
public void shouldReturnCorrectSum() {
    // GIVEN
    int a = 2, b = 3;

    // WHEN
    int result = addition(a, b);

    // THEN
    assertEquals(5, result);
}
```

---

## 3. 🧰 Frameworks de tests par langage

| Langage    | Frameworks principaux      |
| ---------- | -------------------------- |
| Java       | JUnit 5, AssertJ, Mockito  |
| Python     | PyTest, unittest, mock     |
| JavaScript | Jest, Mocha, Cypress (E2E) |
| PHP        | PHPUnit                    |

### Concepts communs :

* `@BeforeEach`, `@AfterEach` : setup/teardown
* Assertions : `assertEquals`, `assertTrue`, `assertThrows`, etc.
* Suites de tests automatisables

---

## 4. 🔌 Gestion des dépendances (Mocks, Stubs)

### Pourquoi ?

* Éviter de tester les composants externes (base de données, API)

### Types :

| Type     | Description                          | Exemple              |
| -------- | ------------------------------------ | -------------------- |
| **Mock** | Simulation avec vérification d’usage | Mockito.verify(...)  |
| **Stub** | Valeur de retour prédéfinie          | retourne "OK"        |
| **Fake** | Implémentation simplifiée pour test  | In-memory repository |

### Exemple en Java (Mockito) :

```java
UserService mockService = mock(UserService.class);
when(mockService.getUsername(1)).thenReturn("admin");
```

---

## 5. 📊 Couverture de tests

### Définition :

Pourcentage de code **exécuté par les tests**.

### Types de couverture :

* **Lignes** : nombre de lignes exécutées
* **Branches** : nombre de conditions `if`, `else`, etc.
* **Chemins** : combinaisons d’exécution possibles
* **Conditions** : toutes les valeurs booléennes possibles

### Outils :

| Langage | Outil              |
| ------- | ------------------ |
| Java    | **JaCoCo**         |
| Python  | **Coverage.py**    |
| JS      | **Istanbul / nyc** |

### Limites :

* 100% ≠ qualité
* On peut exécuter sans vérifier

---

## 6. 🔁 Tests de non-régression

### Définition :

Tester tout le périmètre après chaque évolution pour **vérifier qu’aucune fonctionnalité n’a été cassée**.

### Bonnes pratiques :

* Automatiser avec GitLab/GitHub Actions
* Avoir un référentiel de tests métiers clés
* Marquer les anciens tests comme critiques

---

## 7. 🔐 Tests de sécurité

### Objectif :

Détecter les vulnérabilités connues automatiquement ou manuellement :

* Injections SQL, XSS, CSRF
* Failles de logique métier
* Droits d’accès non respectés

### Méthodes :

* **Tests automatisés** : outils comme OWASP ZAP, SonarQube avec plugins de sécurité
* **Tests manuels** : fuzzing, intrusion simulée (pentest)
* **Unitaires** : vérifier le rejet d’un accès non autorisé

---

## 8. 🔄 Intégration continue (CI) et automatisation

### Étapes CI standard :

1. Pull/Push → GitLab Runner / GitHub Actions
2. Exécution des tests unitaires
3. Rapport de couverture
4. Déclenchement du build et déploiement si succès

### Extrait `.gitlab-ci.yml`

```yaml
test:
  stage: test
  script:
    - ./mvnw test
    - ./mvnw jacoco:report
```

### Ajout d’un **badge de couverture** :

* GitLab : dans les settings du projet
* GitHub : via Coveralls, Codecov…

---

## 🔧 Travaux pratiques

### **TP1** : Tests unitaires sur une classe CRUD

* Créer une classe `UserService`
* Tester `addUser`, `deleteUser`, `getUser`

### **TP2** : Ajout de mocks

* Simuler une API `EmailService` qui envoie des mails

### **TP3** : Rapport de couverture

* Utiliser **JaCoCo** pour générer un rapport HTML
* Analyser les lignes non couvertes

### **TP4** : Automatisation

* CI avec **GitLab Runner**
* Ajout des étapes `test`, `jacoco:report`, `docker build`

### **TP5 (bonus)** : Test de sécurité

* Utiliser **OWASP ZAP** en ligne de commande dans le pipeline
* Détecter des vulnérabilités basiques sur une route `/login`
