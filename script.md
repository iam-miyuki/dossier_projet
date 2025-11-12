### **1. Introduction (30 sec)**

>Bonjour, je m’appelle Miyuki CHERBAL.
Avant cette formation, j’étais femme au foyer.
Avant de venir en France, j’étais photographe scolaire au Japon, et j’ai fait mes études en histoire de l’art là-bas.
J’ai choisi cette formation parce que j’avais envie de comprendre le domaine du web, de savoir comment fonctionne un site internet et comment le développer.
Aujourd’hui, je vais vous présenter mon projet : Tosho.

---

### **2. Présentation du projet (1 min)**

>Tosho veut dire “bibliothèque” ou “livre” en japonais.
C’est une application web que j’ai créée pour une association japonaise dont je fais partie. Cet association est dirigée par des parents bénévoles.
Elle propose des cours de japonais pour des enfants d’origine japonaise, et possède une petite bibliothèque.
Aujourd’hui, pour gérer les prêts de livres, nous utilisons une application web qui a été développée par un ancien parent bénévole il y a plusieurs années.
Cette application fonctionne, mais elle a plusieurs limites.
Par exemple, pour ajouter un nouveau livre dans le catalogue des livres, il faut contacter le développeur initial, parce qu'il n’y a pas d’accès administrateur.
L’interface est aussi très simple, sans CSS, donc pas très intuitive.
Comme je suis parent bibliothécaire de l'association, j’ai eu l’idée de refaire complètement l’application, pour améliorer la gestion, la rendre plus moderne et plus autonome.

---

### **3. Conception du projet (10 min)**

Objectif et MVP

L’objectif principal de Tosho est de permettre aux parents bibliothécaires de gérer facilement les prêts et les retours de livres, et de disposer d’une interface administrateur.

Le MVP se concentre sur les fonctionnalités essentielles :

Enregistrer un prêt et un retour et également rechercher les prêts par livre ou par famille.

Ces fonctionnalités sont indispensables pour que l’application remplisse sa mission principale.

En parallèle, la création d’une interface administrateur était un objectif important, car elle apporte tout le sens à la refonte du l'application. Elle permet aux bénévoles de travailler de manière autonome sans dépendre d’un intervation de dévéloppeur initial.

Il y a deux types d’utilisateurs :

– Les administrateurs, qui gèrent les familles, les livres, les sessions d'inventaire et les bibliothécaires. Les comptes ne peuvent pas être créés librement : seul un administrateur peut créer un compte bibliothécaire.
– Et les bibliothécaires, qui enregistrent les prêts et les retours, et participent à l’inventaire annuel des livres.

Chaque rôle a accès à des fonctionnalités spécifiques, ce qui garantit la sécurité et le bon fonctionnement de la bibliothéque.

Fonctionnalités principales

Pour les bibliothécaires, il y a deux fonctionnalités principales.

Premièrement, la gestion des prêts et retours de livres.
Chaque livre possède un code unique créé par l’association.
Grâce à ce code, les bénévoles peuvent rechercher un livre, vérifier son statut, puis enregistrer un prêt ou un retour.
Il est aussi possible de rechercher un livre par mot-clé, ou une famille par son nom, afin de lui prêter ou rendre un livre.

Deuxièmement, la gestion de l’inventaire.
Les livres de l’association sont répartis dans quatre lieux différents.
Lors de l’inventaire annuel, les administrateurs créent une session d’inventaire pour chaque lieu.
Les bibliothécaires vérifient alors la présence des livres et peuvent signaler des problèmes, par example un livre abîmé, mal rangé, ou sans étiquette.

Pour les admins

Les admins disposent de quatre grandes fonctionnalités :

Gestion des livres — ils peuvent ajouter, consulter, modifier ou supprimer les livres.

Gestion des familles — avec les mêmes actions de création, modification ou suppression.

Gestion des sessions d’inventaire — ils peuvent créer une session en définissant la date et le lieu, et suivre son état : ouverte, à venir, fermée ou terminée.
Une fois la session ouverte, ils peuvent consulter l’avancement, voir les livres vérifiés ou signalés par les bibliothécaires, et mettre à jour le statut de livre signalé après avoir réglé le problem.

Gestion des bibliothécaires — seuls les administrateurs peuvent créer des comptes.
Lorsqu’un nouveau bibliothécaire est ajouté, il reçoit un email automatique l’informant de la création de son compte et de son mot de passe provisoire.
Il pourra ensuite se connecter et modifier son mot de passe.

Enfin, pour superviser la gestion de la bibliothèque, un bouton de bascule permet à l’administrateur de passer directement à l’interface bibliothécaire, afin de tester ou de suivre les opérations.

Contraintes principales

L’application devait répondre à plusieurs contraintes :

L’interface devait rester simple et intuitive, adaptée à des bénévoles non techniques.

L’accès aux fonctionnalités est restreint selon le rôle :
les administrateurs a accès à toutes les fonctionnalités, et les bibliothécaires que les prêts des livres et l'inventaire.

Enfin, les données doivent être fiables et mises à jour en temps réel, pour éviter les erreurs de double prêt ou les livres manquants.

#### **Organisation**

Pour la conception de Tosho, j’ai commencé par lister toutes les fonctionnalités que je voulais développer.
À partir de là, j’ai rédigé un cahier des charges et mes user stories en Markdown, ce qui m’a permis de bien clarifier les besoins avant de passer à la partie visuelle.

Une fois cette base posée, j’ai créé les wireframes et les maquettes sur Figma, pour anticiper la structure de l’application et imaginer le parcours utilisateur.

#### **Charte graphique**

J’ai choisi un design à la fois convivial et ludique, pour que les utilisateurs non techniques — qui sont tous des parents bénévoles — se sentent rapidement à l’aise avec l’outil.

L’identité visuelle de Tosho reflète l’esprit chaleureux de l’association et le côté ludique de l’école japonaise.
Les couleurs principales permettent de différencier les interfaces selon le rôle :

une teinte violette pour les bibliothécaires,

une teinte bleue pour les administrateurs.

L’interface est simple, intuitive et responsive, afin que les parents bénévoles puissent l’utiliser facilement sur mobile comme sur ordinateur.
J’ai également ajouté des icônes au style pixel art, pour donner un aspect ludique et familier, tout en gardant une cohérence graphique avec le logo.

#### **Arborescence**

L’arborescence du site a été pensée pour rester logique et fluide, avec deux espaces bien distincts :

l’espace administrateur,

et l’espace bibliothécaire.

Une fois être connecté à son compte, selon les rôles, les utilisaters atterissent au page d'accueil spécifique:

Les bibliothécaires peuvent enregistrer les prêts et les retours, rechercher un prêt par livre ou par famille, et participer à l’inventaire annuel.

Les administrateurs, eux, ont accès à la gestion complète : les livres, les familles, les sessions d’inventaire, et les bibliothécaires, 

J’ai aussi intégré toutes les pages nécessaires à l’authentification : connexion, réinitialisation de mot de passe, et déconnexion.

Enfin, le site comprend aussi les pages légales classiques, comme les mentions légales, la politique de confidentialité et la gestion des cookies.

#### **Stack technique**

> Tosho utilise :
>
> * **Symfony 6.4** pour le back-end
> * **Twig**, **CSS** et **JavaScript** pour le front
> * **MySQL** pour gestion de base de donné relationnel

#### **MCD**

> Les principales tables :
>
> * `book` : livres
> * `family` : familles
> * `loan` : emprunts
> * `user` : admins et bibliothécaires
inventory : session de l'inventaire
inventoryItem : livre ajouté dans une session de l'inventaire
>   Chaque emprunt relie un **livre** et une **famille**.

---

### **4. Démo (6 à 10 min)**


---

### **5. Front-end (5 min)**

> Pour faciliter la navigation, j'ai mis en place des onglets pour chaque page de fonctionnalité. par example, pour les prêts et les retours des livres, pour que l'accès aux champs de recherche soit claire et pratique, j'ai mis un onglet pour recherche par famill, un autre onglet pour la recherche par livre. 

Pour faciliter l'ajout de livres dans le catalogue, j'ai mis en place d'une foncitonnalité de préremplir le formulaire d'ajout d'un livre. l'utilisateur saisi un code isbn, avec l'api, on récupére les infos sur les livres et préremplir le formulaire. j'ai utilisé deux api différents pour récupérer les donnés différents.
openlibrary pour récupérer les titres et l'auteur en romaji. romaji cest un alphabet latin pour faciliter la lecture en japonais. et l'url de couverture. deuxième api est openBd, c'est un api japonais, pour récupérer les titres et les auteurs en japonais. cette fonctionnalité est développé avec framework js Stimulus. cette fonctionnalité a augmenté la qualité de l'experience user.

> * responsive avec des `media queries` est aussi pensé. sur l'ecran mobile, les composants sont adapté correctement.

---

### **6. Back-end (5 min)**

> Pour le back, j’ai utilisé le modèle **MVC** de Symfony.
> Exemple : quand on fait un prêt.
>
> * Le contrôleur reçoit les données du formulaire.
> * Il crée un nouvel objet **Loan**.
> * Doctrine enregistre dans la base MySQL.
> * La page affiche le prêt.
>   C’est un exemple simple de **CRUD** : créer, lire, modifier, supprimer.

---

### **7. Test (2-3 min)**

---

### **8. Roadmap (1 min)**

> Pour la suite, j’aimerais ajouter :
>
> * une vraie **connexion sécurisée** avec rôles
> * un **historique des prêts** pour chaque famille
> * une **recherche avancée**
> * et peut-être un **QR code** pour enregistrer les livres plus vite.

---

### **9. Conclusion (3 min)**

> J’ai rencontré des difficultés, surtout avec les **relations entre tables** et le **contrôleur**.
> J’ai trouvé des solutions grâce à la **documentation Symfony** et **Stack Overflow**.
> Par exemple, pour un problème de jointure, j’ai trouvé une réponse en anglais et je l’ai adaptée à mon projet.
>
> Ce projet m’a appris à **organiser mon travail**, à **structurer mon code**, et à **comprendre Symfony**.
>
> Je suis très content d’avoir créé une application utile, pour une vraie école.
> Tosho aide les bénévoles à gagner du temps et à mieux gérer la bibliothèque.
> C’est un projet dont je suis fier.
