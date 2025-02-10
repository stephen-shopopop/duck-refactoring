---
layout: center
---

# Quand refactorer ?

---

# La règles des trois

Il n’est pas toujours simple de savoir à quel moment il est nécessaire de commencer à refactorer son code.
Une règle simple a été popularisée par Martin Fowler : la règle de trois. Elle peut se résumer ainsi:

- Lorsque vous faites quelque chose pour la première fois, faites-le.
- Lorsque vous faites quelque chose de similaire pour la seconde fois, rechignez à devoir répéter mais faites-le quand même.
- Lorsque vous faites quelque chose pour la troisième fois, il est temps de commencer la refactoring !

---

# Les autres moment pour engager un refactoring

- Quand un code est considéré comme “sale” (cf. slideq sur le clean code/bad code)
- Quand un code est incompréhensible. C’est utile pour soi, ainsi que pour les développeurs qui interviendront après vous sur ce code.
- Pour préparer l’ajout d’une nouvelle fonctionnalité. En effet, une application informatique est de qualité lorsque le coût d’ajout d’une fonctionnalité reste stable.
- Quand on corrige un bug
- Lors d’une phase de code review
- Quand on a “le temps de le faire” :)
- Quand on souhaite faire évoluer en profondeur notre application (nouvelle architecture ou nouvelle stack technique par exemple)

---

# Attention

Ces arguments (en particulier les trois premiers) sont souvent difficilement recevables de la part des clients.
Pour eux, l’application est en production et elle fonctionne, donc ce n’est pas utile.
Ce travail est pourtant indispensable pour que l’application conserve une bonne hygiène.
Le mieux est de leur expliquer que cela facilitera l’ajout de fonctionnalités futures, en permettant de gagner du temps.

[“Design Stamina Hypothesis” de Martin Fowler](https://martinfowler.com/bliki/DesignStaminaHypothesis.html)

**Attention tout de même à ne pas aller trop loin et à ne pas tomber dans le refactoring permanent !**

---
layout: center
---

# Comment refactorer ?

---
layout: center
---

## Avant tout, il est INDISPENSABLE d’avoir des tests unitaires, sinon comment être sur de ne rien casser lors du refactoring ?!

---

# Les étapes du refactoring

L’idéal est d’essayer de travailler par petites touches, pour ne pas se perdre et pour pouvoir mesurer plus facilement les impacts (positifs ou négatifs). En effet, revoir l’intégralité du système à chaque fois n’a que peu d’intérêt et sera la plupart du temps contre-productif (et compliqué !).

Il existe plusieurs niveaux de refactoring (ordonnés par difficulté):

1. Élimination du code mort.
2. Modification de la présentation (commentaires, mise en page, indentation, normalisation…) et globalement écriture et/ou mise à jour des documentations techniques (schéma d’architectures par exemple).
3. Déplacement, réorganisation et renommage du code.
4. Modification de l’algorithmie.
5. Refonte de la conception.

**Pour les trois premiers points, il ne faut pas hésiter à utiliser les outils proposés par votre IDE !**

---

# Les points 3, 4 et 5

on peut s’appuyer sur des principes ou des bonnes pratiques reconnus par la communauté des développeurs

- **SOLID:** acronyme représentant 5 principes de base pour la POO.
- **YAGNI (You Aren’t Gonna Need It):** principe incitant à ne pas ajouter une fonctionnalité tant que l’on en a pas absolument nécessaire. Attention, ce principe doit-être manipulé avec précaution et nécessite le plus souvent une solide analyse.
- **DRY (Don’t Repeat Yourself):** philosophie consistant à éviter la redondance de code dans une application. Selon la définition officielle, “dans un système, toute connaissance doit avoir une représentation unique, non ambiguë et faisant autorité”.
- **KISS (Keep It Simple, Stupid) et LIM (Less Is More):** concepts non spécifiques au domaine de l’informatique (existe aussi dans l’art, l’architecture, la littérature…) prônant la simplicité en se libérant au maximum des artifices qui ne sont pas essentiels. Il implique de faire des choix et de se poser les bonnes questions pour éviter autant que possible toute complexité non indispensable.
- **Loi de Demeter (Don’t Talk to Strangers):** notion fondamentale indiquant qu’un objet doit éviter de faire des hypothèses à propos de la structure d’autres éléments, y compris ses propres sous-composants

---

# Autres approches

Une approche peut aussi être d’essayer d’améliorer certaines métriques de votre application :
Complexité cyclomatique:

- Taux de couverture de code
- Nombre de lignes de code
- Index de stabilité et de maintenabilité
- …

La procédure serait de réaliser une analyse de code pour obtenir des scores de base, de réaliser une opération de refactoring puis de relancer une analyse pour comparer l’évolution des scores (sans oublier le passage des tests unitaires !).

<br>

**Il est important de comprendre que le refactoring est efficace quand il est ciblé, correctement défini et limité dans le temps !**

---
layout: center
---

# Anti-patterns et codes smells

---

# Codes smells

De la même manière que les design patterns, les codes smells sont identifiés et répertoriés:

- **Duplicated Code:** son nom est sans équivoque et c’est l’un des plus faciles à identifier (manuellement ou via des outils) et le plus souvent assez simple à corriger.
- **Feature Envy:** lorsqu’une méthode d’une classe fait un usage abusif des éléments d’une ou plusieurs autres classes (au moins plus que ses propres éléments). Dans ce cas, il est probable que cette méthode ne soit pas à sa place.
- **God Class/Object:** élément possédant trop de responsabilités au sein d’une même classe.
- **Les bloaters** sont du code, des méthodes ou des classes ayant pris des proportions gigantesques et qui sont devenues incompréhensibles et très difficilement maintenable. Il peut aussi s’agir d’une trop grande liste de paramètres pour une seule méthode.
- **Change preventers:** une modification a un endroit du code implique de réaliser de multiples changements à d’autres endroits. Cela rend la maintenance complexe et coûteuse.
- **Premature optimization:** il s’agit de la volonté de vouloir commencer à optimiser du code juste après l’avoir écrit, avant même de savoir si celui-ci pose réellement un problème.

---

# Anti-patterns logiciel

- **Golden Hammer:** réutiliser de manière obsessionnelle une technologie familière ou maitrisée et ce, même si celle-ci n’est pas la plus adaptée.
- **Boat Hanchor:** composant inutilisé mais qui est conservé dans le logiciel “au cas où”, pour plus tard.
- **Infinite Loop:** c’est une boucle qui contient uniquement une instruction testant une condition. Tant que cette condition n’est pas vérifiée, alors le thread attend. C’est généralement un autre process qui va faire que la condition est remplie et que le programme pourra continuer son déroulement. C’est un gaspillage car le programme va consommer de la ressource “pour rien”. Il vaut mieux utiliser des méthodes comme les événements ou les signaux.
- **Deadlock et famine:** mauvaise conception sur des blocs concurrentiels.
- **Input Kludge:** dans une application acceptant des entrées utilisateur, aucune vérification n’est effectuée avant d’utiliser les données saisies. C’est le meilleur moyen de causer des bugs voir même des failles de sécurité.
- **Coulée de lave:** du code encore immature est mis en production. De fait, cela va fortement compliquer les évolutions futures car on va devoir partir sur un socle (= la lave solidifiée) inadapté. Cela se produit souvent lorsque ce qui était initialement un POC se retrouve à devoir partir en production “en l’état”.

---

# Anti-patterns architecture

- **Reinvent the Wheel:** en particulier si c’est mal réinventé :D Attention, je ne dis pas qu’il ne faut jamais le faire, mais il est nécessaire de bien réfléchir et d’avoir une vue la plus exhaustive de l’état de l’art.
- **Architecture As Requirements:** concevoir une architecture par simple préférence ou parce qu’elle est nouvelle, alors qu’il n’y en a pas le besoin ou l’intérêt.
- **Swiss Army Knife:** il s’agit d’un produit excessivement complexe dont l’auteur a voulu le faire matcher avec le maximum de situation possible. A l’usage, il s’avère le plus souvent difficile et son fonctionnement est le plus souvent obscur et mal maitrisé.

**Il existe aussi des anti-patterns au niveau de la gestion de projet [see this](https://sourcemaking.com/design_patterns)**
