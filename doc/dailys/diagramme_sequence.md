<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
<a href="/doc/liste_dailys.md">
  <img src="../../assets/button/previous_page.png" alt="Back to top" style="width: 150px; height: auto;">
</a>

![border](../../assets/line/border_deco_rt.png)

# UML - Diagramme de séquences

## Sommaire

- [x] Découverte du diagramme de séquences
  - [ ] Comprendre ses objectifs
  - [ ] Identifier les différents éléments
    - [ ] Les acteurs
  - [ ] Les messages
    - [ ] Comprendre et représenter les messages synchrones
    - [ ] Comprendre et représenter les messages asynchrones
    - [ ] Comprendre et représenter les messages auto-référencées
  - [x] [Comprendre et savoir utiliser les structures](#comprendre-et-savoir-utiliser-les-structures)
    - [ ] La structure alt
    - [ ] La structure opt
    - [ ] La structure loop
    - [ ] La structure par
    - [ ] La structure ref
- [ ] Comprendre le passage du diagramme de classes au diagramme de séquences
  - [ ] Comment passer de l'un à l'autre
  - [ ] Lien entre les classes et les acteurs
  - [ ] Comprendre l'utilité pour les développeurs
  - [ ] Comprendre la possibilité de génération de code
- [ ] Cas pratiques :
  - [ ] Modéliser le diagramme de séquences pour un système de réservation dans un restaurant
  - [ ] Modéliser le diagramme de séquences pour la réservation d'un livre dans une bibliothèque

<!-- ![border](assets/line/line_pink_point_l.png) -->

![border](../../assets/line/line-pink-point_l.png)

## Comprendre et savoir utiliser les structures

Voici des explications plus précises pour chaque opérateur **UML** dans un **diagramme de séquence**, avec 200 caractères supplémentaires et en abordant les subtilités comme **`<0..*>`** ou d’autres notations spécifiques.

---

### **1. Alt (alternative)**

- **Alt** représente un **if/else**. Chaque section possède une condition `[condition]`. L'une des branches est exécutée si sa condition est vraie.
- Le **`else`** gère l’autre cas.

**Exemple UML** :

```plaintext
alt [x > 10]
   actionA()
else [x <= 10]
   actionB()
end alt
```

- Ici, `actionA` ou `actionB` sera exécutée selon la valeur de `x`.

---

---

### **2. Opt (option)**

- **Opt** est comme un `if` sans `else`. Le bloc est **exécuté uniquement** si la condition est vraie.
- Si la condition est fausse, le bloc est simplement ignoré.

**Exemple UML** :

```plaintext
opt [userLoggedIn]
   showProfile()
end opt
```

- Ici, `showProfile()` s'exécute seulement si `userLoggedIn` est vrai.

### **1. Acteurs et objets**

- **Acteurs** : Représentent les entités externes qui interagissent avec le système (utilisateurs, systèmes tiers).
- **Objets** : Placés en haut, chaque objet a une ligne de vie verticale symbolisant sa durée d'existence.

---

### **2. Message simple et synchrone**

- **Message synchrone** : La flèche pleine pointe vers le destinataire. L’émetteur **attend** la réponse avant de continuer.
- **Message asynchrone** : Une flèche avec pointe ouverte, l’émetteur **n’attend pas**.

---

### **3. Message de retour**

- Une **flèche en pointillés** retourne vers l’émetteur. Elle indique qu’une opération a été exécutée et que des résultats (ou un état) sont renvoyés à l’objet appelant.

---

### **4. Loop (boucle)**

- Le bloc **loop** exécute un groupe d'interactions de manière **répétée** tant qu'une condition `[condition]` est vraie.
- **`<0..*>`** signifie qu’une interaction peut être répétée **0 ou plusieurs fois**, selon la condition.

**Exemple UML** :

```plaintext
loop [i < 5]
   action()
end loop
```

- Le `<0..*>` précise le nombre d'itérations possibles (0 fois si la condition est immédiatement fausse).

---

### **7. Par (parallèle)**

- **Par** représente des interactions **parallèles**. Les branches séparées par `and` s’exécutent **simultanément**.
- Cela peut montrer plusieurs processus ou threads.

**Exemple UML** :

```plaintext
par
   downloadFile()
and
   showProgress()
end par
```

- Les deux méthodes `downloadFile()` et `showProgress()` s’exécutent en même temps.

---

### **8. Ref (référence)**

- **Ref** appelle un **autre diagramme de séquence** déjà défini. Cela évite de **répéter** les interactions complexes.

**Exemple UML** :

```plaintext
ref AuthenticationSequence
```

- Cela signifie que le diagramme actuel fait appel à un sous-diagramme "AuthenticationSequence".

---

### **9. Break (interruption)**

- **Break** interrompt **immédiatement** la séquence en cas de condition spécifique. Le reste du bloc est ignoré.

**Exemple UML** :

```plaintext
break [errorOccurred]
   displayError()
end break
```

- `displayError()` s’exécute si `errorOccurred` est vrai. La séquence s’arrête là.

---

### **10. Critical (section critique)**

- **Critical** bloque tout accès concurrentiel aux actions dans ce bloc pour éviter les **problèmes de synchronisation**.

**Exemple UML** :

```plaintext
critical
   writeToFile()
end critical
```

- Ici, `writeToFile()` est protégé contre toute exécution parallèle.

---

### **11. Création et destruction d’objets**

- **Création** : Une flèche pointe vers l’objet créé avec une **ligne de vie** démarrant au moment de l'appel.
- **Destruction** : Une **croix (X)** au bas de la ligne indique la **fin de vie** de l’objet.

**Exemple UML** :

```plaintext
create ObjectX
ObjectX -> destroy
```

---

### **Résumé de `<0..*>` et autres notations**

- **`<0..*>`** : Exécution entre **0 et un nombre infini** de fois (boucle facultative).
- **`<1..*>`** : Au moins une exécution requise.
- **`<n..m>`** : Exactement **n à m itérations**.

---

Ces subtilités permettent de détailler précisément le **comportement** d’un diagramme de séquence, notamment en introduisant des boucles, des alternatives conditionnelles et des interactions parallèles.

<a href="#sommaire">
  <img src="../../assets/button/back_to_top.png" alt="Back to top" style="width: 150px; height: auto;">
</a>
<a href="/README.md">
  <img src="../../assets/button/home_page.png" alt="Home page" style="width: 150px; height: auto;">
</a>
