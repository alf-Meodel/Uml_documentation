<a href="../../README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
<a href="../../doc/liste_dailys.md">
  <img src="../../assets/button/previous_page.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../../assets/line/border_deco_rt.png)

```
include : obligatoire
exclude :
```

https://agilemodeling.com/style/usecasediagram.htm

```
use case = user stories

```

# Diagrammes de cas d'utilisation et diagramme de classes

## Sommaire

- [x] Faire les objectifs de la veille

- [x] Découverte avancé des cas d'utilisation (les relations)
  - [x] Comprendre la notion d'association
  - [x] Comprendre et représenter le terme d'inclusion
  - [x] Comprendre et représenter le terme d'extension
  - [x] Comprendre et représenter la généralisation
- [x] Découverte du diagramme de classes
  - [x] Etude générale du diagramme de classes
    - [x] Objectifs
  - [x] Dans quels cas est-il utilisé ?
  - [x] Etudier la représentation d'une classes
    - [x] Son formalisme
  - [x] Les attributs
  - [x] Les méthodes
  - [x] L'encapsulation
  - [x] Etudier les différences avec le MCD de la méthode MERISE
- [ ] Cas pratique
  - [ ] Réaliser le diagramme de cas d'utilisation d'une société de réservation de taxis
  - [ ] Réaliser le diagramme de classes d'une bibliothèque

## Tools

- [Video diagramma d'activité ](https://www.youtube.com/watch?v=MbCDYFWWwEo)

<!-- ![border](assets/line/line_pink_point_l.png) -->

![border](../../assets/line/line-pink-point_l.png)

## Découverte avancé des cas d'utilisation (les relations)

## Notion d'association :

#### Définition :

L'association est une relation entre deux éléments (acteurs ou cas d'utilisation) qui interagissent entre eux. Elle est souvent représentée par une ligne simple entre les éléments concernés.

#### Exemple :

- Dans un système de gestion d’hôpital, un patient (acteur) est associé au cas d’utilisation prendre rendez-vous.
- Représentation UML : Une ligne relie l’acteur Patient au cas d’utilisation Prendre rendez-vous.

```
Patient ------> Prendre rendez-vous
```

## Comprendre la notion d'association

### Comprendre et représenter le terme d'inclusion

## Terme d'inclusion :

#### Définition :

L'inclusion est utilisée lorsqu'un cas d'utilisation en appelle un autre, parce qu'il est obligatoire pour son exécution. Cela permet de réutiliser des fonctionnalités communes.

- Mot-clé UML : <<include>>

#### Exemple :

- Dans un système de réservation, le cas d’utilisation Payer la réservation inclut le cas d’utilisation Vérifier les informations de paiement.
- Cela signifie que le paiement ne peut pas se faire sans la vérification des informations.

```
Payer la réservation ----<<include>>----> Vérifier les informations de paiement
```

### Comprendre et représenter le terme d'extension

### Définition :

- L'extension est utilisée lorsqu’un cas d’utilisation est facultatif et dépend d'une condition. Il permet d’ajouter des fonctionnalités spécifiques sous certaines conditions.
- Mot-clé UML : <<extend>>
- Exemple :
- Dans un système d’e-commerce, le cas d’utilisation Finaliser la commande peut être étendu par le cas d’utilisation Appliquer un code promo si l’utilisateur entre un code promotionnel.

```
Finaliser la commande ----<<extend>>----> Appliquer un code promo
```

### Comprendre et représenter la généralisation

## Généralisation :

- Définition : La généralisation est utilisée pour représenter une relation hiérarchique ou d’héritage entre des éléments. Un cas d’utilisation ou un acteur peut hériter des propriétés d’un autre.

## Exemple :

- Un acteur Administrateur peut être une généralisation des acteurs Gestionnaire de comptes et Gestionnaire de contenu.
- De même, le cas d'utilisation Gérer les utilisateurs peut être généralisé par Créer un utilisateur, Modifier un utilisateur, et Supprimer un utilisateur.

```
            Administrateur
           /              \
Gestionnaire de contenu  Gestionnaire de comptes
```

![border](../../assets/line/line-teal-point_r.png)

---

<a href="#sommaire">
  <img src="../../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>
<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
