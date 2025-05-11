## 🎓 CHAPITRE-03 – La méthode Merise : MCD, MLD, MPD

### 🎯 Objectifs pédagogiques :

* Comprendre la méthode Merise et son rôle dans la conception de bases de données relationnelles
* Maîtriser la modélisation conceptuelle (MCD), logique (MLD) et physique (MPD)
* Être capable de concevoir une base de données normalisée et prête à être implémentée

---

#### 1. Introduction à Merise

* Contexte historique et origine
* Vue d’ensemble de la méthode : cycle de vie du système d'information
* Les trois niveaux de modélisation : conceptuel, logique, physique
* Place de Merise dans la gestion de projet SI

#### 2. Le Modèle Conceptuel des Données (MCD)

* Entités, associations, cardinalités
* Attributs, identifiants
* Règles de modélisation (entité faible, relation réflexive, etc.)
* Cas particuliers : association ternaire, héritage
* **TP** : MCD d’une bibliothèque, d’une école, ou d’un hôpital

#### 3. Le Modèle Logique des Données (MLD)

* Transformation du MCD en MLD
* Tables, clés primaires, clés étrangères
* Normalisation (1NF, 2NF, 3NF)
* Intégrité référentielle
* **TP** : Passage d’un MCD vers un MLD et vérification de la normalisation

#### 4. Le Modèle Physique des Données (MPD)

* Définition des types de données (SQL : VARCHAR, INT, DATE, etc.)
* Contraintes (PRIMARY KEY, FOREIGN KEY, NOT NULL)
* Création des tables avec SQL
* Optimisation de la structure physique (index, performances)
* **TP** : Implémentation d’un MPD dans MySQL / PostgreSQL

#### 5. Cas d’étude global

* Sujet de projet (ex : gestion d’une université, d’un stock, d’un réseau social simple)
* Réalisation complète : MCD → MLD → MPD → Requêtes SQL

---

### 🔧 Travaux pratiques

* **TP1** : Élaboration du MCD à partir d’un cahier des charges simple
* **TP2** : Passage MCD → MLD et détection des anomalies de modélisation
* **TP3** : Génération du MPD avec SQL (manuelle et/ou via un outil comme Workbench ou PgModeler)
* **TP4** : Rédaction de requêtes SQL de création, insertion, mise à jour, et sélection
