![image](https://github.com/user-attachments/assets/c33c2f49-b653-4964-96f3-0895edd6ccc9)


### 1. **Dépendance (Dependency)**
**Définition** : Une classe utilise une autre classe de manière temporaire. La dépendance est faible.

```java
class A {
    void useB() {
        B b = new B();
        b.display();
    }
}

class B {
    void display() {
        System.out.println("Class B is being used by Class A");
    }
}

public class DependencyExample {
    public static void main(String[] args) {
        A a = new A();
        a.useB(); // A utilise B temporairement
    }
}
```

**Explication** : La classe `A` crée une instance locale de la classe `B` dans sa méthode `useB`, montrant une relation de dépendance.

---

### 2. **Agrégation (Aggregation)**
**Définition** : Une classe contient une autre classe comme un attribut. Les deux peuvent exister indépendamment.

```java
class A {
    private B b;

    public A(B b) {
        this.b = b;
    }

    void show() {
        b.display();
    }
}

class B {
    void display() {
        System.out.println("Class B is aggregated in Class A");
    }
}

public class AggregationExample {
    public static void main(String[] args) {
        B b = new B();  // B peut exister seul
        A a = new A(b); // B est "agrégé" dans A
        a.show();
    }
}
```

**Explication** : La classe `A` a une instance de `B` passée en tant que paramètre dans le constructeur. L'objet `B` peut être utilisé ailleurs.

---

### 3. **Composition**
**Définition** : Une classe possède une autre classe comme attribut, mais leur cycle de vie est lié (si A est détruit, B est détruit).

```java
class A {
    private B b = new B();

    void show() {
        b.display();
    }
}

class B {
    void display() {
        System.out.println("Class B is owned by Class A");
    }
}

public class CompositionExample {
    public static void main(String[] args) {
        A a = new A();
        a.show();
        // B est détruit quand A est détruit
    }
}
```

**Explication** : Ici, la classe `A` crée l'objet `B` directement dans son attribut. La relation est plus forte que l'agrégation.

---

### 4. **Héritage (Inheritance)**
**Définition** : Une classe dérivée hérite des propriétés et méthodes d'une classe de base.

```java
class A {
    void display() {
        System.out.println("Class A: Parent class");
    }
}

class B extends A {
    @Override
    void display() {
        super.display();
        System.out.println("Class B: Child class");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        B b = new B();
        b.display(); // Méthode héritée et surchargée
    }
}
```

**Explication** : La classe `B` hérite de `A` et peut utiliser ses méthodes tout en les redéfinissant grâce à l'annotation `@Override`.

---

### 5. **Réalisation (Realization)**
**Définition** : Une classe implémente les méthodes d'une interface.

```java
interface A {
    void display();
}

class B implements A {
    @Override
    public void display() {
        System.out.println("Class B realizes interface A");
    }
}

public class RealizationExample {
    public static void main(String[] args) {
        A a = new B(); // Interface utilisée comme type
        a.display();
    }
}
```

**Explication** : La classe `B` réalise (implémente) l'interface `A`, obligeant `B` à fournir une implémentation pour les méthodes de `A`.

---

![image](https://github.com/user-attachments/assets/933c3cb6-ead1-4aa1-bcee-a82a2768072f)  



### Multiplicité :   


![image](https://github.com/user-attachments/assets/bdcafd2f-0129-4fae-a074-470fcc5e8160)



### Exemple de code
```java
import java.util.ArrayList;
import java.util.List;

// Classe représentant une entreprise
class Company {
    private String name;
    private List<Person> employees; // Une entreprise peut avoir plusieurs personnes (1..*)

    public Company(String name) {
        this.name = name;
        this.employees = new ArrayList<>();
    }

    // Ajouter une personne à l'entreprise
    public void addEmployee(Person person) {
        if (person.getCompany() != null) {
            System.out.println("Cette personne est déjà associée à une autre entreprise.");
        } else {
            employees.add(person);
            person.setCompany(this); // Liaison bidirectionnelle
        }
    }

    public String getName() {
        return name;
    }

    public List<Person> getEmployees() {
        return employees;
    }
}

// Classe représentant une personne
class Person {
    private String name;
    private Company company; // Une personne est associée à une seule entreprise (1)

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public Company getCompany() {
        return company;
    }

    public void setCompany(Company company) {
        if (this.company == null) { // Une personne ne peut être associée qu'à une seule entreprise
            this.company = company;
        } else {
            System.out.println("Cette personne est déjà employée par " + this.company.getName());
        }
    }
}

// Exemple d'utilisation
public class Main {
    public static void main(String[] args) {
        // Création d'une entreprise
        Company company = new Company("TechCorp");

        // Création de personnes
        Person person1 = new Person("Alice");
        Person person2 = new Person("Bob");

        // Ajout de personnes à l'entreprise
        company.addEmployee(person1); // Alice rejoint TechCorp
        company.addEmployee(person2); // Bob rejoint TechCorp

        // Affichage des employés de l'entreprise
        System.out.println("Les employés de " + company.getName() + " :");
        for (Person p : company.getEmployees()) {
            System.out.println("- " + p.getName());
        }

        // Tentative de réaffectation d'une personne à une autre entreprise
        Company anotherCompany = new Company("OtherCorp");
        anotherCompany.addEmployee(person1); // Cela échouera car Alice est déjà employée par TechCorp
    }
}
```

### Explications :
1. **Multiplicité `1` pour `Person -> Company`** :
   - Une personne ne peut être associée qu'à une seule entreprise grâce à la vérification dans la méthode `setCompany`.

2. **Multiplicité `1..*` pour `Company -> Person`** :
   - Une entreprise peut avoir plusieurs employés. La liste `employees` dans la classe `Company` permet de gérer cette relation.

3. **Relations bidirectionnelles** :
   - Lorsqu'une personne est ajoutée à une entreprise, l'entreprise est aussi définie comme employeur pour la personne.



---------------


## Aller plus loin : 

### 1. Association
Une association indique une relation structurelle entre deux classes, signifiant que des objets d'une classe sont liés à des objets d'une autre classe. Elle est représentée par une ligne continue entre les classes concernées. Les associations peuvent être unidirectionnelles (avec une flèche indiquant la direction) ou bidirectionnelles (sans flèche).

**Exemple :**
```plaintext
[Classe A] ───────── [Classe B]
```

### 2. Héritage (Généralisation)
L'héritage, ou généralisation, décrit une relation hiérarchique où une classe enfant hérite des attributs et méthodes d'une classe parent. Cette relation est représentée par une ligne continue avec une flèche creuse pointant vers la classe parent.

**Exemple :**
```plaintext
[Classe Parent] ◄────── [Classe Enfant]
```

### 3. Agrégation
L'agrégation représente une relation « tout/partie » où une classe est composée de plusieurs instances d'une autre classe, sans dépendance forte entre elles. Elle est illustrée par une ligne continue avec un losange creux du côté de la classe « tout ».

**Exemple :**
```plaintext
[Classe Tout] ◇─────── [Classe Partie]
```

### 4. Composition
La composition est une forme stricte d'agrégation où la classe « partie » ne peut exister sans la classe « tout ». Elle est représentée par une ligne continue avec un losange plein du côté de la classe « tout ».

**Exemple :**
```plaintext
[Classe Tout] ◆─────── [Classe Partie]
```

### 5. Dépendance
Une dépendance indique qu'une classe dépend de l'autre pour fonctionner, généralement parce qu'elle utilise ses méthodes ou attributs. Elle est représentée par une ligne pointillée avec une flèche pointant vers la classe dont elle dépend.

**Exemple :**
```plaintext
[Classe Dépendante] - - - - ▻ [Classe Indépendante]
```

### 6. Multiplicité
La multiplicité précise le nombre d'instances d'une classe pouvant être associées à une instance d'une autre classe. Elle est indiquée par des annotations près des extrémités des associations.

**Notations courantes :**
- `1` : Exactement une instance.
- `0..1` : Zéro ou une instance.
- `*` ou `0..*` : Zéro ou plusieurs instances.
- `1..*` : Au moins une instance.

**Exemple :**
```plaintext
[Classe A] 1 ──────── * [Classe B]
```
Cela signifie qu'une instance de la Classe A peut être associée à plusieurs instances de la Classe B, mais chaque instance de la Classe B est associée à une seule instance de la Classe A.

Pour une illustration complète de ces relations avec leurs notations UML, vous pouvez consulter le [guide complet sur les diagrammes de classes UML](https://www.cybermedian.com/fr/a-comprehensive-guide-to-uml-class-diagram/).      



### 🔁 **Association Réflexive en UML**

---

### 🔹 Définition :

Une **association réflexive** (ou **auto-association**) en UML est une **relation entre une classe et elle-même**.

> Cela signifie qu'un objet peut être en relation avec **un ou plusieurs autres objets** de **la même classe**.

---

### 🔸 Cas d’usage typique :

* Un **employé** peut **manager** d'autres **employés**.
* Un **dossier** peut contenir d'autres **dossiers**.
* Une **personne** peut avoir une **relation familiale** avec une autre personne (même classe).

---

### 📐 Exemple UML (diagramme de classes) :

```plantuml
@startuml
class Employe {
  - nom : String
}

Employe "1" -- "0..*" Employe : manage
@enduml
```

👉 Ici :

* Chaque `Employe` peut **manager plusieurs employés**
* Chaque `Employe` peut être **managé par un seul autre employé**

---

### 💻 Exemple en Java :

```java
import java.util.List;
import java.util.ArrayList;

public class Employe {
    private String nom;
    private Employe manager;
    private List<Employe> subordonnes;

    public Employe(String nom) {
        this.nom = nom;
        this.subordonnes = new ArrayList<>();
    }

    public void setManager(Employe manager) {
        this.manager = manager;
        manager.ajouterSubordonne(this);
    }

    public void ajouterSubordonne(Employe e) {
        subordonnes.add(e);
    }

    public void afficherStructure() {
        System.out.println("Employé : " + nom);
        if (manager != null) {
            System.out.println("  Manager : " + manager.nom);
        }
        if (!subordonnes.isEmpty()) {
            System.out.println("  Subordonnés : ");
            for (Employe e : subordonnes) {
                System.out.println("    - " + e.nom);
            }
        }
    }
}
```

### 🧪 Utilisation :

```java
public class Main {
    public static void main(String[] args) {
        Employe alice = new Employe("Alice");
        Employe bob = new Employe("Bob");
        Employe charlie = new Employe("Charlie");

        bob.setManager(alice);
        charlie.setManager(alice);

        alice.afficherStructure();
        bob.afficherStructure();
    }
}
```

---




## Documentation : 

https://www.edrawsoft.com/fr/article/uml-aggregation-vs-composition.html


