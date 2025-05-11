# CHAPITRE-01 – L'Agilité et le Framework Scrum

## 🌟 Objectifs pédagogiques

* Comprendre les origines et principes de l'agilité
* Identifier les rôles, événements et artefacts du framework Scrum
* Savoir mettre en œuvre Scrum dans un contexte de projet logiciel
* Préparer à la certification Scrum (PSM I ou équivalent)

---

## 1. Introduction à l'agilité

### 1.1 Contexte historique et limites des méthodes traditionnelles

Avant l'apparition des méthodes agiles, le développement logiciel était majoritairement régi par des modèles linéaires comme le cycle en V ou le Waterfall (en cascade). Ces approches, adaptées aux projets industriels, sont rigides et reposent sur des spécifications figées au départ, avec peu de place pour les changements en cours de route.

#### Limites principales :

* Long délai entre spécification et livraison
* Difficultés à répondre aux changements
* Faible implication du client pendant le projet
* Risque élevé de décalage entre besoin réel et solution délivrée

### 1.2 Le Manifeste Agile (2001)

Les fondateurs de l'agilité ont formulé 4 valeurs fondamentales :

* Les individus et leurs interactions **plus que** les processus et les outils
* Un logiciel fonctionnel **plus que** une documentation exhaustive
* La collaboration avec le client **plus que** la négociation contractuelle
* L'adaptation au changement **plus que** le suivi d'un plan

Et 12 principes dérivés, comme :

* Livrer fréquemment un logiciel fonctionnel
* Accueillir favorablement les changements, même tardifs
* Travailler au quotidien avec le client

### 1.3 Comparaison agile vs classique

| Critère            | Méthode classique        | Méthode agile            |
| ------------------ | ------------------------ | ------------------------ |
| Planification      | Détaillée, définitive    | Adaptative, incrémentale |
| Implication client | Minime                   | Continue                 |
| Livraison          | Unique, en fin de projet | Régulière, incrémentale  |
| Documentation      | Complète                 | Légère, ciblée           |

### 1.4 Quand (ne pas) utiliser l'agilité ?

**Appropriée quand :**

* Projet incertain ou innovant
* Client disponible et impliqué
* Besoin de livraisons rapides et adaptables

**Moins adaptée si :**

* Projet fortement réglementé (aéronautique, médical)
* Spécifications figées et stables

---

## 2. Panorama des méthodes agiles

### 2.1 Scrum

Le framework agile le plus répandu dans le développement logiciel. Il se concentre sur la livraison rapide et incrémentale d'un produit fonctionnel.

### 2.2 Kanban

Approche visuelle de gestion de flux de travail. Moins prescriptive que Scrum, elle vise l'amélioration continue et la limitation du travail en cours (WIP).

### 2.3 Extreme Programming (XP)

Met l'accent sur les pratiques techniques : tests unitaires, intégration continue, programmation en binôme.

### 2.4 SAFe / LeSS

Frameworks agiles à l'échelle, pour coordonner plusieurs équipes Scrum dans des projets complexes ou des organisations entières.

---

## 3. Scrum en détail

### 3.a Rôles Scrum

* **Scrum Master** : Facilitateur de l'équipe, garant de la méthodologie
* **Product Owner (PO)** : Responsable du Product Backlog, porte la vision du client
* **Developers** : Équipe auto-organisée chargée de livrer l'incrément

### 3.b Événements Scrum (Cercles de transparence)

* **Sprint** : Itération fixe (1 à 4 semaines)
* **Sprint Planning** : Objectif du sprint et backlog du sprint
* **Daily Scrum** : Réunion de 15 minutes pour synchroniser l'équipe
* **Sprint Review** : Démonstration du produit, retour du client
* **Sprint Retrospective** : Amélioration du fonctionnement de l'équipe

### 3.c Artefacts Scrum

* **Product Backlog** : Liste priorisée de tout ce qu'on souhaite pour le produit
* **Sprint Backlog** : Ensemble des user stories sélectionnées pour le sprint
* **Incrément** : Fonctionnalités prêtes, conformes à la DoD
* **Definition of Done (DoD)** : Critères pour considérer une tâche comme terminée

### 3.d Cycle complet d’un Sprint

1. Le PO définit les priorités du Product Backlog
2. Sprint Planning : l’équipe choisit les User Stories à réaliser
3. Daily Scrum quotidien
4. Livraison de l’incrément
5. Sprint Review + Sprint Retrospective
6. Recommencer le cycle

---

## 🔧 Travaux pratiques (TP)

### TP1 : Lecture du Manifeste Agile

* Activité : Lecture collective + discussion guidée
* Objectif : Comprendre les principes et ouvrir un débat sur leur pertinence actuelle

### TP2 : Simulation d'un projet Scrum (2 sprints)

* Activité : Jeu de rôles avec un mini-projet (ex : application TODO)
* Objectif : Se familiariser avec les événements et rôles Scrum

### TP3 : Création d'un Product Backlog + DoD

* Activité : Brainstorming des besoins puis rédaction des User Stories
* Objectif : Structurer le backlog et définir les critères de qualité attendus

### TP4 : Atelier de rédaction Agile (Epic, Feature, User Story, Tasks)

* Exemple décomposé :

  * **Epic** : Gérer les comptes utilisateurs
  * **Feature** : Inscription avec vérification par email
  * **User Story** : En tant qu’utilisateur, je veux recevoir un email de confirmation après inscription afin de valider mon compte
  * **Tasks** : Créer le formulaire, gérer l’envoi d’email, implémenter la vérification
