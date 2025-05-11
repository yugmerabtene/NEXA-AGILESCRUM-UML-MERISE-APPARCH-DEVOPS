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

## 🎓 CHAPITRE-04 – Architecture Applicative : MVC & Microservices

### 🎯 Objectifs pédagogiques :

* Comprendre les principes d’organisation d’une application logicielle
* Identifier les différences entre architecture monolithique, MVC et microservices
* Appliquer les principes d’une architecture adaptée aux besoins d’un projet
* Préparer le terrain pour le développement backend et frontend structuré

---

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

---

