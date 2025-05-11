## 🎓 CHAPITRE-01 – L’Agilité et le Framework Scrum

### 🎯 Objectifs pédagogiques :

* Comprendre les origines et principes de l’agilité
* Identifier les rôles, événements et artefacts du framework Scrum
* Savoir mettre en œuvre Scrum dans un contexte de projet logiciel
* Préparer à la certification Scrum (PSM I ou équivalent)

---
#### 1. Introduction à l’agilité

* Origine : contexte historique et limites des méthodes traditionnelles (cycle en V, waterfall)
* Le Manifeste Agile : les 4 valeurs et 12 principes
* Comparaison : méthodes agiles vs méthodes classiques
* Quand (ne pas) utiliser une méthode agile ?

#### 2. Panorama des méthodes agiles

* Scrum : le plus utilisé dans les projets IT
* Kanban : flux de travail visuel et optimisation continue
* XP (Extreme Programming) : pratiques techniques agiles
* SAFe / LeSS : frameworks agiles à l’échelle

#### 3. Scrum en détail

##### a. Rôles Scrum

* Scrum Master : facilitateur, garant du cadre
* Product Owner : voix du client, responsable du Product Backlog
* Developers (équipe de développement) : auto-organisée et multidisciplinaire

##### b. Événements Scrum (les "cercles de transparence")

* Sprint (itération de 1 à 4 semaines)
* Sprint Planning (planification du Sprint)
* Daily Scrum (mêlée quotidienne)
* Sprint Review (revue de fin de Sprint)
* Sprint Retrospective (amélioration continue)

##### c. Artefacts Scrum

* Product Backlog : liste priorisée des besoins
* Sprint Backlog : plan d’action du Sprint
* Incrément : valeur ajoutée à chaque Sprint
* Definition of Done (DoD) : critères de qualité et de complétion

##### d. Le cycle complet d’un Sprint

* Du besoin client à la livraison d’un produit fonctionnel

---

### 🔧 Travaux pratiques

* **TP1** : Lecture commentée du Manifeste Agile et débat en groupe
* **TP2** : Simulation d’un projet en Scrum sur 2 sprints (avec rôles attribués à chaque étudiant)
* **TP3** : Atelier de rédaction de User Stories (format : *En tant que... Je veux... afin de...*)
* **TP4** : Élaboration d’un Product Backlog et définition d’une DoD

---

### 📌 Supports complémentaires

* Quiz Agile vs Waterfall
* Modèle de fiche rôle Scrum (PO, SM, Dev)
* Modèle de Sprint Board (physique ou Trello/Jira)
* Liens vers simulateurs Scrum interactifs
* Préparation à un mini-examen blanc type PSM I

---

## 🎓 CHAPITRE-02 – Introduction à l’UML et aux principaux diagrammes

### 🎯 Objectif pédagogique :

Comprendre les fondements de l’UML (Unified Modeling Language) et maîtriser les quatre principaux types de diagrammes utilisés dans l’analyse et la conception orientée objet.

---

#### 1. Introduction à UML

* Historique et contexte d’apparition
* Objectifs et utilité dans le développement logiciel
* Avantages de l’UML dans les projets agiles et traditionnels
* Outils de modélisation (StarUML, Modelio, etc.)

#### 2. Diagramme de cas d’utilisation (Use Case)

* Définition et rôle dans l’analyse fonctionnelle
* Acteurs et cas d’utilisation
* Portée du système
* Relations (include, extend, généralisation)
* Bonnes pratiques
* **TP** : Modéliser les cas d’utilisation d’une application de gestion de bibliothèque

#### 3. Diagramme de séquence (Sequence Diagram)

* Objectif : représenter l’interaction temporelle entre les objets
* Objets, messages, activation, conditions
* Boucles, alternatives, parallélisme
* Couplage avec les cas d’utilisation
* **TP** : Diagramme de séquence pour un emprunt de livre

#### 4. Diagramme d’activité (Activity Diagram)

* Représentation des flux de processus ou d’algorithmes métier
* Nœuds d'action, décisions, forks/joins, événements
* Différence avec le diagramme de flux classique
* Cas d’usage typique : processus métier ou fonction d’un use case
* **TP** : Diagramme d’activité du retour d’un livre

#### 5. Diagramme de classes (Class Diagram)

* Fondement de la modélisation orientée objet
* Classes, attributs, méthodes
* Associations, héritage, agrégation, composition
* Multiplicités, visibilités, types
* Liens avec les autres diagrammes (Use Case → Classe, Séquence → Classe)
* **TP** : Modéliser les classes d’un système de gestion de bibliothèque

---

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

---

## 🎓 CHAPITRE-04 – Architecture Applicative : MVC & Microservices

### 🎯 Objectifs pédagogiques :

* Comprendre les principes d’organisation d’une application logicielle
* Identifier les différences entre architecture monolithique, MVC et microservices
* Appliquer les principes d’une architecture adaptée aux besoins d’un projet
* Préparer le terrain pour le développement backend et frontend structuré

---

### 🗂 Plan détaillé du chapitre :

#### 1. Introduction à l’architecture logicielle

* Définition d’une architecture logicielle
* Pourquoi structurer une application ?
* Critères de choix : scalabilité, maintenabilité, découplage, performance
* Comparaison des grandes familles (Monolithique, N-Tiers, SOA, Microservices)

#### 2. Architecture MVC (Model - View - Controller)

* Principe du modèle MVC
* Rôle de chaque couche :

  * **Model** : logique métier, accès aux données
  * **View** : interface utilisateur
  * **Controller** : gestion des requêtes et coordination
* Illustration avec des frameworks : Spring (Java), Django (Python), Laravel (PHP)
* Avantages et limites
* **TP** : Décomposer une application CRUD en MVC

#### 3. Architecture en couches (Layered Architecture)

* Séparation en couches : présentation, métier, données
* Relation entre MVC et architecture en couches
* Respect des responsabilités et découplage des modules
* **TP** : Définir les couches d’une application de gestion d’utilisateur

#### 4. Architecture Microservices

* Définition et principes fondamentaux
* Services indépendants, communication via API (REST/gRPC), base de données propre à chaque service
* Conteneurisation (Docker), orchestrateurs (Kubernetes)
* Exemple typique : Auth, Users, Orders, Payments...
* Comparaison : Monolithique vs Microservices
* Défis : transactions distribuées, communication, monitoring
* **TP** : Modéliser un système e-commerce en microservices

---

### 🔧 Travaux pratiques

* **TP1** : Représenter une architecture MVC et associer les composants
* **TP2** : Comparer deux architectures applicatives (MVC vs Microservices) selon un cas donné
* **TP3** : Schéma d’architecture d’une application déployée avec des microservices (diagramme, dépendances, flux API)
* **TP4** : Simulation de communication entre services avec Postman ou FastAPI

Parfait, voici une proposition de **syllabus structuré pour un CHAPITRE-04 – Architecture Applicative : MVC et Microservices**. Ce chapitre vise à introduire les grands modèles d’architecture utilisés dans les applications modernes.

---

Excellent choix pour un CHAPITRE-05, voici un **syllabus complet sur les tests unitaires et la couverture de tests**, indispensable pour garantir la qualité du code dans tout projet professionnel.

---

## 🎓 CHAPITRE-05 – Tests unitaires et couverture de tests

### 🎯 Objectifs pédagogiques :

* Comprendre l’intérêt et les principes fondamentaux des tests unitaires
* Apprendre à écrire des tests efficaces, maintenables et automatisés
* Mesurer la couverture de tests et interpréter les résultats
* Utiliser des frameworks de tests adaptés selon les langages (JUnit, PyTest, etc.)

---

#### 1. Introduction au test logiciel

* Pourquoi tester ?
* Types de tests : unitaires, d’intégration, fonctionnels, E2E
* Cycle de vie des tests dans un projet (TDD, BDD)
* Bonnes pratiques générales

#### 2. Les tests unitaires

* Définition : tester une unité (fonction, méthode) indépendamment
* Ce qu’on teste / Ce qu’on ne teste pas
* Cas de test : données valides, limites, erreurs
* Structure d’un test : *Given / When / Then*
* **TP** : Écrire des tests simples sur des fonctions métiers (addition, tri, etc.)

#### 3. Frameworks de tests (par langage)

* **Java** : JUnit 5, AssertJ, Mockito
* **Python** : unittest, pytest, mock
* **JavaScript** : Jest, Mocha
* **PHP** : PHPUnit
* Setup, assertions, organisation des tests

#### 4. Gestion des dépendances dans les tests

* Mocks, Stubs, Fakes
* Injection de dépendances pour faciliter les tests
* Test des exceptions et comportements anormaux
* **TP** : Utilisation de mocks pour isoler les composants

#### 5. La couverture de tests

* Définition : pourcentage du code exécuté par les tests
* Types de couverture : lignes, branches, chemins, conditions
* Mesure avec outils (ex. : JaCoCo, Coverage.py, Istanbul)
* Limites : une couverture élevée ≠ qualité des tests
* **TP** : Générer un rapport de couverture et analyser les zones non couvertes

#### 6. Intégration continue et automatisation des tests

* Tests dans un pipeline CI/CD
* Exécution automatique des tests à chaque push / pull request
* Badge de couverture et seuils qualité
* **TP** : Mise en place d’un pipeline simple avec GitHub Actions ou GitLab CI

---

### 🔧 Travaux pratiques

* **TP1** : Tests unitaires sur une classe de gestion d’utilisateurs (CRUD)
* **TP2** : Ajout de mocks pour un service dépendant d’une API externe
* **TP3** : Rapport de couverture de tests et actions correctives
* **TP4** : Intégration des tests dans un dépôt Git avec automatisation

---

## 🎓 CHAPITRE-06 – DevOps et pipeline CI/CD : tests, build et déploiement

### 🎯 Objectifs pédagogiques :

* Comprendre la culture DevOps et ses bénéfices dans le cycle de vie logiciel
* Savoir configurer un pipeline CI/CD complet et sécurisé
* Automatiser les tests, la compilation, l’intégration et le déploiement
* Maîtriser les outils principaux : GitHub Actions, GitLab CI, Jenkins, Docker...

---

### 🗂 Plan détaillé du chapitre :

#### 1. Introduction au DevOps

* Définition et objectifs : collaboration Dev + Ops
* Cycle de vie logiciel en DevOps
* Comparaison DevOps vs méthodes traditionnelles
* Outils phares de l’écosystème (CI/CD, conteneurs, infra as code...)

#### 2. Intégration Continue (CI)

* Déclencheurs (push, PR, merge)
* Phase de **tests automatisés** : unitaires, intégration, sécurité (linters)
* Génération de rapports (couverture, logs)
* Outils : GitHub Actions, GitLab CI, Jenkins
* **TP** : Créer un job de test avec badge de succès

#### 3. Build automatisé

* Compilation et packaging du code (Java, Node, Python...)
* Résolution des dépendances
* Versioning et artéfacts
* Outils : Maven, Gradle, npm, Docker Build
* **TP** : Générer automatiquement une image Docker avec version taguée

#### 4. Livraison Continue (CD)

* Déploiement automatisé : staging, production
* Déploiement sur VPS, Cloud, containers (Docker, K8s)
* Stratégies de déploiement : blue/green, rolling update, canary
* Sécurisation des déploiements (SSH, secrets, GitOps)
* **TP** : Déploiement automatique sur un serveur après merge

#### 5. Monitoring et feedback

* Logs, erreurs, métriques post-déploiement
* Outils : Prometheus, Grafana, ELK, Sentry
* Alertes et rollback automatisé (selon seuils critiques)
* **TP** : Intégrer une alerte basique ou un rapport de logs

---

### 🔧 Travaux pratiques

* **TP1** : Écriture d’un pipeline CI/CD simple (YAML) avec tests et build
* **TP2** : Déploiement automatique d’une API ou app web sur un VPS avec Docker
* **TP3** : Utilisation de secrets pour sécuriser un pipeline
* **TP4** : Mise en place d’un badge de statut + rapport de couverture de test
