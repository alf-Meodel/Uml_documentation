<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
<a href="/doc/liste_dailys.md">
  <img src="../../assets/button/previous_page.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../../assets/line/border_deco_rt.png)

# Diagramme de classes

## Sommaire

- [ ] Finir les objectifs de la veille

- [x] Approfondir les connaissances sur le diagramme de classes
  - [ ] Comprendre la notion d'association
  - [ ] Etudier les différentes multiplicités et leur signification
  - [ ] Comprendre l'agrégation (losange vide)
  - [ ] Comprendre la composition (losange plein)
  - [ ] Etudier les différences entre les 2
  - [ ] Intégrer les packages
- [ ] Comprendre l'héritage
  - [ ] Savoir représenter un généralisation / une spécialisation
  - [ ] Représenter une classe abstraite
  - [ ] Représenter une interface
- [ ] Savoir lire un diagramme de classes complets

- [ ] Cas pratiques
  - [ ] Modéliser un système pour gérer les activités d'un cinéma (films, salles, séances)
  - [ ] Modéliser la gestion d'une école
  - [ ] Modéliser un système de gestion de projets (projets, équipes, membres, tâches, sous tâches)

<!-- ![border](assets/line/line_pink_point_l.png) -->

![border](../../assets/line/line-pink-point_l.png)

## Comprendre la notion d'association

![cas_utilisation](/assets/img/association.png)

### Définition :

Une association relie deux classes pour indiquer qu'elles interagissent ou sont connectées d'une certaine manière.

### Représentation UML

Une ligne simple entre deux classes, souvent annotée avec un nom de relation et parfois des rôles.

### Exemple :

Une classe Personne peut être associée à une classe Voiture par une relation "possède".

```
Une association dans un diagramme de classes UML représente une relation
entre deux ou plusieurs classes. Elle indique que des objets d'une classe
sont liés à des objets d'une autre classe.
```

## Exemple :

Une classe Professeur est associée à une classe Cours, ce qui signifie qu'un professeur peut enseigner un ou plusieurs cours.

## Caractéristiques :

Elle peut être unidirectionnelle (A connaît B) ou bidirectionnelle (A et B se connaissent).
Elle peut inclure un nom d'association pour indiquer la nature de la relation.

![border](../../assets/line/line-pink-point_l.png)

## Etudier les différentes multiplicités et leur signification

### Un peu comme dans Merise

```
Dans UML, la multiplicité est notée directement sur la ligne de relation.
Dans Merise, la cardinalité est indiquée entre parenthèses
 à côté des entités associées.
```

### Représentation UML :
Indiquée par des nombres ou des plages aux extrémités de la ligne d'association.

_1 :_ Une seule instance (relation 1:1).
0.._ : Aucune ou plusieurs instances (relation 1:N ou N:N).
1.._ : Au moins une instance.

## Comprendre l'agrégation ( losange vide)

![cas_utilisation](/assets/img/agrégation_composite.png)

**Agrégation composite** : Une relation forte où la vie du tout (composite) dépend de ses parties. Si le tout est détruit, les parties le sont aussi. Représentée par un losange plein dans un diagramme UML.

![cas_utilisation](/assets/img/agrégation_partagée.png)

**Agrégation partagée** : Une relation faible où les parties peuvent exister indépendamment du tout. Représentée par un losange vide dans UML.

![border](../../assets/line/line-pink-point_l.png)

## Comprendre la composition (losange plein)

### Définition :

Une composition est une relation "tout-partie" forte où la partie dépend totalement du tout.

### Représentation UML :
Un losange plein à l'extrémité du "tout".

### Exemple :

Une Maison contient des Pièces. Si la maison est détruite, les pièces le sont également.

###

---

---

La **composition** dans un diagramme UML est une relation forte entre deux classes, où l'une (le tout) possède l'autre (la partie), et la durée de vie de la partie dépend entièrement de celle du tout.

### **Définition Simplifiée**

- **Relation forte** : Si le tout est détruit, ses parties le sont aussi.
- **Représentation UML** : Un **losange plein** à l'extrémité de la classe "tout".

---

### **Cas concret : Une Maison et ses Pièces**

#### **1. Classes impliquées**

- Classe `Maison` (le tout) :
  - Attributs : `adresse`, `nombreDePièces`.
- Classe `Pièce` (la partie) :
  - Attributs : `type` (exemple : chambre, salon), `superficie`.

#### **2. Relation entre les classes**

- Une maison est composée de pièces.
- Si la maison est détruite, les pièces n'ont plus de raison d'exister.

#### **Diagramme UML**

```
Maison ◼─── Pièce
```

- Le losange **plein** est côté `Maison`.
- Multiplicité :
  - Côté `Maison` : `1` (chaque pièce appartient à une seule maison).
  - Côté `Pièce` : `0..*` (une maison peut avoir zéro ou plusieurs pièces).

---

---

---

![border](../../assets/line/line-pink-point_l.png)

## Etudier les différences entre les 2

![border](../../assets/line/line-pink-point_l.png)

---

---

### Différences détaillées entre **Agrégation** et **Composition** dans UML

L’agrégation et la composition sont deux types de relations "tout-partie" dans les diagrammes UML, mais elles diffèrent dans la **force** de la relation et la **dépendance** entre le tout et ses parties.

---

| **Critère**               | **Agrégation (losange vide)**                                     | **Composition (losange plein)**                                      |
| ------------------------- | ----------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Nature de la relation** | Relation faible (association "tout-partie" non exclusive).        | Relation forte (association "tout-partie" exclusive et obligatoire). |
| **Dépendance**            | Les parties peuvent exister indépendamment du tout.               | Les parties dépendent entièrement du tout pour leur existence.       |
| **Durée de vie**          | La destruction du tout n’entraîne pas la destruction des parties. | La destruction du tout entraîne automatiquement celle des parties.   |
| **Partage des parties**   | Les parties peuvent être partagées entre plusieurs "tout".        | Les parties appartiennent exclusivement à un "tout".                 |
| **Représentation UML**    | Losange vide sur la classe "tout".                                | Losange plein sur la classe "tout".                                  |
| **Exemple**               | Une bibliothèque contient des livres.                             | Une maison contient des pièces.                                      |

---

---

---

## Intégrer les packages

![border](../../assets/img/packages.png)

### Définition :

Les packages permettent de regrouper des classes liées pour mieux organiser un système complexe.

### Représentation UML :

Un rectangle avec un onglet supérieur gauche portant le nom du package.

### Exemple :

Un package GestionSalles peut contenir des classes Salle, Équipement, Projection.

![border](../../assets/line/line-teal-point_r.png)

---

<a href="#sommaire">
  <img src="../../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>
<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
