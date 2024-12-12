# UML

<!-- Main image  -->

![border](./assets/line/border_deco_rt.png)

# Sommaire

- [Introduction](#introduction)
- [Eléments structurels](#1-éléments-structurels)
- [Eléments comportementaux](#2-éléments-comportementaux)
- [Relations liens-entre-éléments](#3-relations-liens-entre-éléments)
- [Eléments d'interaction](#4-éléments-dinteraction)
- [Eléments de groupement](#5-éléments-de-groupement)

# Navigation

- [Liste des dailys](./doc/liste_dailys.md)

![border](./assets/line/line-teal-point_r.png)

# Introduction

Les différents éléments présents dans l'UML (Unified Modeling Language) peuvent être regroupés en catégories selon leur rôle dans les **diagrammes structurels**, **comportementaux**, et **d'interaction**. Voici une explication détaillée de chaque type d'élément et de son rôle :

---

### Généralités

### 1. **Éléments Structurels**

Ces éléments représentent la structure statique du système.

| Élément            | Description                                                                                                     |
| ------------------ | --------------------------------------------------------------------------------------------------------------- |
| **Classe**         | Représente un objet dans le système, avec ses attributs et méthodes.                                            |
| **Attribut**       | Une propriété d'une classe (exemple : `nom`, `âge` dans une classe Personne).                                   |
| **Méthode**        | Une fonction ou opération qu'une classe peut exécuter (exemple : `seConnecter()`).                              |
| **Interface**      | Spécifie un contrat ou un ensemble de méthodes qu’une classe doit implémenter.                                  |
| **Association**    | Montre une relation entre deux classes (exemple : "Un client passe une commande").                              |
| **Généralisation** | Représente une relation d'héritage entre classes (exemple : `Animal → Chien`).                                  |
| **Composition**    | Relation "partie-tout" où la partie ne peut exister sans le tout (exemple : une voiture contient un moteur).    |
| **Agrégation**     | Relation "partie-tout" où les parties peuvent exister indépendamment (exemple : un département a des employés). |
| **Objet**          | Une instance d'une classe (exemple : une classe `Personne` peut avoir un objet `Jean`).                         |
| **Composant**      | Représente un module logiciel ou une brique du système.                                                         |
| **Noeud**          | Représente une entité physique (serveur, machine virtuelle).                                                    |

---

### 2. **Éléments Comportementaux**

Ces éléments montrent la dynamique et les interactions entre les différentes parties du système.

| Élément               | Description                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------- |
| **Acteur**            | Représente un utilisateur ou un système externe interagissant avec le système.                     |
| **Cas d'utilisation** | Décrit une fonctionnalité ou une interaction spécifique du système (exemple : "Réserver un vol").  |
| **Message**           | Représente une communication entre objets ou acteurs dans un diagramme de séquence.                |
| **État**              | Représente une condition dans laquelle un objet peut se trouver (exemple : "connecté", "inactif"). |
| **Transition**        | Montre le passage d'un état à un autre (exemple : "En attente → En cours").                        |
| **Action**            | Une tâche ou opération réalisée pendant une transition ou un état.                                 |
| **Activité**          | Représente un processus ou un workflow (exemple : "vérifier la disponibilité d’un produit").       |
| **Swimlane**          | Divise un diagramme d'activité en zones pour montrer les responsabilités des différents acteurs.   |

---

### 3. **Relations (Liens entre éléments)**

Les relations représentent les connexions entre les différents éléments UML.

| Relation                    | Description                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------- |
| **Dépendance**              | Indique qu'un élément dépend d'un autre pour fonctionner.                                   |
| **Association**             | Relie deux éléments pour montrer qu'ils collaborent ou interagissent.                       |
| **Généralisation**          | Relation "est un(e)" pour l'héritage ou la spécialisation (exemple : `Oiseau → Aigle`).     |
| **Réalisation**             | Indique qu'une classe implémente une interface ou un contrat.                               |
| **Composition**             | Relation forte entre le tout et ses parties (le tout ne peut pas exister sans les parties). |
| **Agrégation**              | Relation faible entre le tout et ses parties (les parties peuvent exister indépendamment).  |
| **Déclenchement (Trigger)** | Une action ou événement qui déclenche une transition d'état ou un processus.                |

---

### 4. **Éléments d'Interaction**

Ces éléments montrent comment les objets ou acteurs interagissent.

| Élément              | Description                                                                          |
| -------------------- | ------------------------------------------------------------------------------------ |
| **Ligne de vie**     | Représente la durée de vie d’un objet ou d’un acteur dans un diagramme de séquence.  |
| **Fragment**         | Définit une interaction ou une condition particulière dans un diagramme de séquence. |
| **Objet (Instance)** | Représente une instance spécifique d'une classe qui participe à une interaction.     |
| **Retour (Return)**  | Montre le message ou la donnée renvoyée par un objet suite à une interaction.        |

---

### 5. **Éléments de Groupement**

Ces éléments aident à organiser les diagrammes.

| Élément                 | Description                                                                                               |
| ----------------------- | --------------------------------------------------------------------------------------------------------- |
| **Paquetage (Package)** | Regroupe des classes ou des composants similaires pour organiser le système.                              |
| **Bordure du système**  | Délimite ce qui est inclus ou exclu du système, souvent utilisé dans les diagrammes de cas d’utilisation. |

---

### Exemple simple : Diagramme de classes

```plaintext
+--------------------+       +-----------------+
|       Client       |       |    Commande    |
+--------------------+       +-----------------+
| - nom : String     |<----> | - date : Date  |
| - email : String   |       | - montant : Double|
+--------------------+       +-----------------+
| + passerCommande() |       | + valider()    |
+--------------------+       +-----------------+
```

Dans cet exemple :

- **Classe `Client`** : contient les informations du client et une méthode `passerCommande()`.
- **Classe `Commande`** : contient les détails de la commande et une méthode `valider()`.
- **Association** : montre la relation entre `Client` et `Commande`.

L'objectif principal de chaque élément est de représenter **visuellement** un aspect du système pour en faciliter la compréhension et la conception. 😊

![border](./assets/line/line-pink-point_l.png)

<a href="#sommaire">
<img src="assets/button/back_to_top.png" alt="Home page" style="width: 150px; height: auto;">
</a>

![border](./assets/line/line-teal-point_l.png)

![border](./assets/line/border_deco_rt.png)
