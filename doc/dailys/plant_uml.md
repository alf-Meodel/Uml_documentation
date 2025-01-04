<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
<a href="/doc/liste_dailys.md">
  <img src="../../assets/button/previous_page.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../../assets/line/border_deco_rt.png)

# Plant UML

## Sommaire

- [x] [Structure de base d'un diagramme PlantUML](#structure-de-base-dun-diagramme-plantuml)
- [x] [Acteurs et Participants](#acteurs-et-participants)
- [x] [Envoi de Messages](#envoi-de-messages)
- [x] [Fragments conditionnels : alt et else](#envoi-de-messages)
- [x] [Fragment optionnel : opt](#fragment-optionnel--opt)
- [x] [Boucles : loop](#boucles--loop)
- [x] [Notes](#notes)

- [x] [Exemple complet](#exemple-complet)
- [x] [Rendu visuel](#rendu-visuel)
- [x] [Outils pour tester PlantUML](#outils-pour-tester-plantuml)

<!-- ![border](assets/line/line_pink_point_l.png) -->

![border](../../assets/line/line-pink-point_l.png)

![border](../../assets/line/line-teal-point_r.png)

### Structure de base d'un diagramme PlantUML

Chaque diagramme commence et se termine par :

```
@startuml Nom_Du_Diagramme
# Votre code ici
@enduml
```

- `@startuml` : Indique le début du diagramme.
- `@enduml` : Indique la fin.

---

### Acteurs et Participants

Les **acteurs** et **participants** représentent les éléments qui interagissent dans le diagramme.

- **Acteurs** : Souvent des utilisateurs ou des systèmes externes.
- **Participants** : Objets ou composants impliqués dans l'interaction.

**Syntaxe :**

```
actor Client
participant "Système de Réservation" as SR
participant "Base de Données" as BD
```

- **actor** : Déclare un acteur avec un pictogramme spécial (utilisateur).
- **participant** : Déclare un objet ou un composant du système.
- **as SR** : Permet d'utiliser un alias (raccourci) pour nommer un participant.

---

### Envoi de Messages

Les messages représentent des flèches entre les acteurs et les participants pour décrire les interactions.

**Syntaxe :**

```
Client -> SR : Demande de réservation
SR -> BD : Vérifier disponibilité
BD --> SR : Retourner disponibilité
```

- `->` : Flèche **synchronisée** (attend une réponse).
- `-->` : Flèche **asynchronisée** (ne nécessite pas de réponse immédiate).
- `:` : Permet de nommer le message (texte à afficher).

---

### Fragments conditionnels : `alt` et `else`

Les fragments `alt` permettent de représenter des **conditions** avec des branches alternatives.

**Syntaxe :**

```
alt Condition 1
    SR -> Client : Confirmer disponibilité
else Condition 2
    SR -> Client : Réservation impossible
end
```

- **`alt`** : Indique un fragment conditionnel.
- **`else`** : Permet d'ajouter une branche alternative.
- **`end`** : Termine le fragment conditionnel.

---

### Fragment optionnel : `opt`

`opt` est utilisé pour représenter des actions **optionnelles**.

**Syntaxe :**

```
opt Notification
    SR -> PR : Envoyer notification
end
```

- **`opt`** : Définit une condition optionnelle.
- **`end`** : Termine le fragment.

---

### Boucles : `loop`

Les fragments `loop` permettent de représenter des actions répétées.

**Syntaxe :**

```
loop Tant que place disponible
    SR -> BD : Vérifier disponibilité
end
```

- **`loop`** : Définit un fragment de boucle.
- **`end`** : Termine la boucle.

---

### Notes

Vous pouvez ajouter des **notes** pour commenter ou expliquer certaines étapes.

**Syntaxe :**

```
note right of SR : Ici, on vérifie la base de données.
```

- **`note right/left of Participant`** : Positionne la note à droite ou à gauche.

---

### Exemple complet

```
@startuml Reservation_Restaurant
actor Client
participant "Système de Réservation" as SR
participant "Base de Données" as BD
participant "Personnel du Restaurant" as PR

Client -> SR : Demande de réservation
SR -> BD : Vérifier disponibilité
BD --> SR : Retourner disponibilité

alt Place disponible
    SR -> Client : Confirmer disponibilité
    Client -> SR : Valider réservation
    SR -> BD : Enregistrer réservation
else Place indisponible
    SR -> Client : Réservation impossible
end

opt Notification
    SR -> PR : Envoyer notification
end

note right of SR : La notification est optionnelle.
@enduml
```

---

### Rendu visuel

Ce code génère un **diagramme clair** avec :

- Des **messages synchrones** pour les interactions.
- Un **fragment conditionnel** (`alt`) pour la vérification de disponibilité.
- Un **fragment optionnel** (`opt`) pour la notification.
- Des **notes** pour ajouter des explications.

---

### Outils pour tester PlantUML

1. **[PlantUML Online](https://www.plantuml.com/plantuml/)** : Outil en ligne simple pour générer vos diagrammes.
2. **Intégration VS Code** : Vous pouvez utiliser l'extension **PlantUML** pour générer vos diagrammes directement.
3. **Graphviz** : Utilisé en arrière-plan pour le rendu.

---

![border](../../assets/line/line-pink-point_l.png)

<a href="#sommaire">
  <img src="../../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>
<a href="../../README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
