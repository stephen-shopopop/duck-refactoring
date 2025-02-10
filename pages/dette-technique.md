---
layout: center
---

# Dette technique

Le concept de dette technique peut se résumer ainsi : toute erreur de conception implique des coûts supplémentaires dans le futur. Ces coûts, par analogie avec la dette financière, sont appelés les intérêts. Toute la gestion de la dette technique se résume en une question : souhaite-t-on continuer de rembourser des intérêts ou faut-il solder sa dette une bonne fois pour toutes ?

---
layout: center
---

Ce concept est apparu dans les années 90 par Ward Cunningham (qui est aussi l’inventeur du concept du Wiki). Il représente la mesure de la difficulté à ajouter de nouvelles fonctionnalités et correctifs sur un logiciel.

Cette dette augmente naturellement et inévitablement dès le commencement d’un projet, en particulier à cause du rythme effréné d’évolution des technologies informatiques et des savoir-faire. La dette est aussi corrélée à la taille d’un projet : plus celui est volumineux et plus sa dette va augmenter.

---

# Type de dettes

- **La dette d’opportunité:** on a besoin de faire vite pour être le premier (réduction du time-to-market).
- **La dette d’innovation:** dans l’informatique, la technologie et les usages évoluent très vite (souvent plus vite que les projets) et un bon choix de conception à un moment T peut-être remis en cause à T+1 (nouvelle technologie, obsolescence…).
Ce constat n’est valable qu’à condition de disposer :
  - D’un meilleur état de l’art à l’instant T
  - D’un procédé adéquat permettant de comparer les deux états de l’art
  - D’une connaissance approfondie des objectifs, du contexte et des contraintes auxquelles était initialement assujettie l’équipe
- **La dette d’héritage (legacy):** lorsque l’on travaille sur un ancien système (ou plus généralement un système existant) sur lequel a été empilé des évolutions et des corrections au fur et à mesure du temps (en général par de nombreux développeurs différents).

---
layout: center
---

Cette dette finie par augmenter de manière importante les temps, et donc les coûts, de développement des fonctionnalités ce qui va créer des tensions entre le client (ou tout du moins celui qui paye) et l’équipe qui réalise (~qui développe). Cette dette, quelle qu’elle soit, va donc finir par se transformer en dette financière !

---

# Les effets négatifs de la dette technnique

En effet, travailler avec du “vieux” code ou du code mal écrit, ne pas avoir les bons outils ou les bons frameworks, ne pas pouvoir tester son code… génère des effets de bords :

- Découragement
- Lenteur
- Baisse de motivation (Bore-out)
- Perte de créativité
- Érosion des compétence

<br>

**La dette obscure est un produit de l’augmentation de la complexité et de l’hétérogénéité d’un système, il s’agit d’une dette qui ne se manifeste en général qu’en production par de larges et complexes pannes. Elles sont non décelables à la création mais sont une conséquence d’interactions entre composants logiciels ou matériels.**

---
layout: center
---

# Attention

la dette technique n’est pas forcément mauvaise si elle est correctement maîtrisée (au même titre qu’une dette financière). Mais il est important de garder à l’esprit quelle est inévitable, qu’il faudra la payer un jour et qu’il faut donc apprendre à la maîtriser !

---

# Calculer la dette technique

Il est important de savoir où l’on en est vis-à-vis de la dette technique pour pouvoir réagir et anticiper au bon moment.

Il y a plusieurs méthodes :

- Dans un projet Scrum, diminution de la vélocité de sprint en sprint OU augmentation du nombre d’heures passées par StoryPoint.
- Toujours en Scrum, comparaison du nombre de régressions et/ou bugs par rapport au nombre de StoryPoint livrés par sprint. Si ce ratio augmente, cela peut cacher des soucis.
- Méthode SQUALE (Software Quality Assessment based on Lifecycle Expectations)
- Observation des résultats d’outils de mesure de qualité : taux de couverture de tests, audit de qualité de code… (SonarQube par exemple)

---

# Comment maitriser la dette technique

Une fois que l’on sait où l’on en est par rapport à la dette technique, on peut prendre des mesures pour la maîtriser.

- Limiter le nombre de technologies (pour limiter la complexité de la maintenance de l’application).
- Utiliser des technologies ayant fait leurs preuves et étant reconnues comme stables et maintenues. Attention aux “jeunes” technologies dont on ne connait pas l’avenir…
- Utiliser la technologie qui permettra de répondre au besoin (et pas celle qui est à la mode !).
- Normaliser le code source (style, nommage, organisation…) pour qu’il soit lisible et compréhensible par l’ensemble des développeurs (et ce, peu important le moment auquel ils interviennent).
- Ne pas céder aux sirènes de la généricité, sauf si c’est réellement utile.
- Ne pas négliger les phases de conception, en particulier en début de projet, et s’appuyer sur des experts ainsi que sur l’état de l’art pour vous aider
- Soigner la connaissance et la maîtrise de la stack technologique par l’équipe chargée du développement. De plus, veiller à ce que cette connaissance soit partagée dans l’équipe (éviter les spécialistes d’une brique) via des revues de code, du pair-programming ou des présentations.
- Doser l’effort qualitatif entre trop grande rigueur et laxisme (“un effort juste, pour un effet suffisant”)
- Écrire des tests unitaires (car si l’on ne peut pas tester, on ne va pas prendre le risque d’améliorer le code, c’est bien trop risqué !)
- Budgétiser la baisse de la dette (ou en tenir compte lors des estimations) et investir dans la qualité et l’évolution technologique
