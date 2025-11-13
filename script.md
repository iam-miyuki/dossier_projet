1. Introduction (30 sec)

Bonjour, je m’appelle Miyuki CHERBAL.
Avant cette formation, j’étais femme au foyer.
Au Japon, j’étais photographe scolaire et j’ai fait des études en histoire de l’art.
J’ai choisi cette formation parce que je voulais comprendre comment fonctionne le web et apprendre à développer un site internet.
Aujourd’hui, je vais vous présenter mon projet : Tosho.

2. Présentation du projet (1 min)

“Tosho” signifie “bibliothèque” ou “livre” en japonais.
C’est une application web que j’ai créée pour une association japonaise dont je fais partie. Cette association, dirigée par des parents bénévoles, propose des cours de japonais pour les enfants expatriés et ceux d’origine japonaise. Elle possède une petite bibliothèque et les parents gères les prêts des livres et la gestion de collection.
Actuellement, nous utilisons une application de gestion de bibliothéque développée il y a plusieurs années par un ancien parent bénévole. Elle fonctionne, mais elle a plusieurs limites. Par exemple, pour ajouter un nouveau livre, il faut contacter le développeur initial car il n’y a pas d’accès administrateur. L’interface est très simple, pas de css, et peu intuitive.

Dans l'association, je suis parent bibliothécaire, j’ai eu l’idée de refaire l’application pour faciliter la gestion, la rendre plus moderne et permettre aux bénévoles de travailler de manière autonome.

3. Conception du projet (10 min)

L’objectif principal de Tosho est de permettre aux bibliothécaires de gérer facilement les prêts et les retours de livres, et d’avoir une interface administrateur.

Le MVP se concentre sur les fonctionnalités essentielles : enregistrer un prêt et un retour, et rechercher les prêts par livre ou par famille.

Il y a deux types d’utilisateurs :

Administrateurs : gèrent les familles, les livres, les sessions d’inventaire et les bibliothécaires. Ils sont les seuls à pouvoir créer des comptes.

Bibliothécaires : enregistrent les prêts et les retours, participent à l’inventaire annuel.

Chaque rôle a accès à des fonctionnalités spécifiques, ce qui garantit la sécurité et le bon fonctionnement de la bibliothèque.

Fonctionnalités principales

Pour les bibliothécaires :

Gestion des prêts et retours : chaque livre a un code unique, on peut chercher un livre par code ou par mot-clé, et une famille par son nom.

Gestion de l’inventaire : les livres sont répartis dans plusieurs lieux. Lors de l’inventaire annuel, les bibliothécaires vérifient la présence des livres et signalent les problèmes (livres abîmés, mal rangés, etc.).

Pour les administrateurs :

Gestion des livres et des familles : ajouter, modifier, supprimer.

Gestion des inventaires : créer une session, suivre son avancement, mettre à jour les problèmes signalés.

Gestion des bibliothécaires : créer un compte et envoyer un mail automatique avec un mot de passe provisoire.

Supervision : possibilité de basculer sur l’interface bibliothécaire pour tester ou suivre les opérations.

Contraintes

Interface simple et intuitive pour des bénévoles non techniques.

Accès aux fonctionnalités limité selon le rôle.

Données fiables et mises à jour en temps réel pour éviter les erreurs.

Organisation

J’ai commencé par lister toutes les fonctionnalités et rédiger un cahier des charges avec des user stories.
Ensuite, j’ai créé les wireframes et maquettes sur Figma pour visualiser le parcours utilisateur.

L’identité visuelle de Tosho a été pensée pour refléter l’esprit de l’association scolaire. à la fois ludique, conviviale et accessible.
L’objectif est de proposer une interface simple à comprendre, agréable à utiliser, et adaptée aux parents bénévoles.

J’ai choisi trois couleurs principales :

Le bleu foncé pour le texte, les bordures et les icônes.

Le violet clair pour l’interface des bibliothécaires.

Le bleu clair pour l’interface des administrateurs.

Ces couleurs ont été vérifiées pour garantir une bonne visibilité et un contraste suffisant, afin que tout soit facile à lire et agréable pour les utilisateurs.

L’interface est responsive, avec des icônes style pixel art pour garder un aspect ludique et familier.

Arborescence

L’arborescence du site a été pensée pour être simple et logique.

Depuis la page d’accueil, on accède à la connexion et aux pages statiques, comme les mentions légales ou la politique de cookies.

Après la connexion, l’utilisateur est redirigé vers son espace selon son rôle.

Côté bibliothécaire, on retrouve les pages pour les prêts et retours, l’inventaire et le compte personnel. Sur la page d’accueil, une notification signale les retours en retard.

Côté administrateur, on a un accès complet à la gestion des livres, des familles, des bibliothécaires et des sessions d’inventaire.
Seul l’administrateur peut créer les comptes bibliothécaires.
L'admin a aussi l'accès au espace bibliothécaire.

Stack technique

Pour la partie technique, j’ai utilisé plusieurs technologies.

Côté front-end, j’ai utilisé du HTML avec des balises sémantique pour structurer les pages proprement, et du CSS organisé par composants, avec des variables pour les couleurs et les polices.
Les media queries permettent à l’application de s’adapter aux différentes tailles d’écran.

J’ai utilisé Twig, le moteur de templates de Symfony, pour séparer le code PHP de la partie visuelle, et réutiliser facilement les éléments communs comme le header ou le footer.

En JavaScript, j’ai ajouté des interactions dynamiques, par exemple la preremplissage automatique d’un formulaire d'ajoute de livre à partir de son ISBN, grâce à Stimulus.

Et enfin, côté back-end, l’application tourne avec PHP 8.2, Symfony 6.4 et MySQL.
Symfony gère la base de données, les formulaires, la sécurité et les rôles utilisateurs, ce qui facilite beaucoup le développement et la maintenance.


L’application suit le modèle MVC (Model – View – Controller)propre à Symfony, qui sépare clairement les responsabilités :  
- **Controller (Contrôleur)** : reçoit les requêtes de l’utilisateur, exécute la logique métier et envoie les données vers la vue correspondante.  
- **Model (Modèle)** : gère les entités et communique avec la base de données via **Doctrine ORM**, puis renvoie les données au contrôleur.  
- **View (Vue)** : reçoit les données du contrôleur et génère l’affichage des pages avec **Twig**.

MCD
Pour la conception de la base de données, j’ai d’abord tout dessiné sur papier, pour bien visualiser les tables et leurs relations. 

MPD
Une fois le schéma et la cardinalité validés par mon formateur, je l’ai ensuite traduit en entités Symfony, donc en classes PHP gérées par Doctrine.

Chaque entité correspond à une table de la base de données, avec ses propriétés pour les champs et ses relations avec les autres entités.

Cette étape m’a permis d’obtenir une structure claire, cohérente et facile à maintenir pour la suite du développement.

Sécurité

Pour protéger l’application, j’ai mis en place une gestion des accès basée sur les rôles et autorisations.

Il y a deux rôles principaux :

ROLE_ADMIN qui a un accès complet à toutes les fonctionnalités,

et ROLE_LIBRARIAN qui a un accès restreint, limité aux prêts, retours et inventaire.

Selon le rôle, l’utilisateur est redirigé automatiquement vers son espace grâce à l’AuthenticationSuccessHandler.
Avant chaque connexion, le fichier UserChecker.php vérifie que le compte est bien actif. Si un bibliothécaire a été désactivé, il ne peut plus se connecter.

Ensuite, j’ai mis en place un filtrage des accès pour contrôler ce que chaque utilisateur peut faire.
Côté back-end, j’utilise la méthode isGranted() pour vérifier les permissions sur certaines actions.
Côté front-end, dans Twig, je peux afficher ou masquer des éléments selon le rôle avec {% if is_granted('ROLE_ADMIN') %}.

En résumé, chaque utilisateur voit et peut faire uniquement ce qui correspond à son rôle, ce qui sécurise l’application tout en restant simple à utiliser.

Pour sécuriser les données dans Tosho, j’ai utilisé plusieurs mécanismes intégrés à Symfony.

Toutes les requêtes vers la base passent par Doctrine avec des requêtes préparées. Ça signifie que les données des utilisateurs ne sont jamais insérées directement dans le SQL, ce qui protège contre les injections.

Les formulaires sont aussi protégés par des tokens CSRF : chaque formulaire contient un jeton unique vérifié à l’envoi. Ça permet de s’assurer que seules les actions venant d’utilisateurs authentifiés sont acceptées et empêche les attaques externes.

Comme j’ai utilisé les classes AbstractType et FormType pour créer les formulaires, cette protection est automatique.

En résumé, grâce aux requêtes préparées et aux tokens CSRF, les données restent fiables et sécurisées, et Symfony prend bien en charge cette partie sécurité.

5. Front-end (5 min)

Système d’onglets pour basculer entre les fonctionnalités sans recharger la page.

Formulaires de recherche et d’ajout pour chaque module.

Saisie automatique via ISBN avec OpenBD et OpenLibrary, gérée par Stimulus.

Interface fluide, intuitive et rapide pour les bénévoles.

6. Back-end (5 min)

Gestion des statuts de livres et prêts avec des Enums pour éviter les erreurs.

LoanController centralise les recherches et enregistrements de prêts/retours.

Recherches performantes avec LIKE, en français et japonais.

ParamConverter pour récupérer directement les entités depuis l’URL.

Historique conservé : pas de suppression des données pour garder une traçabilité complète.

7. Deploiement

Au début, j’ai développé Tosho sur Windows avec XAMPP, mais au fil du temps, j’ai remarqué que le chargement des pages était souvent très lent et que XAMPP manquait de stabilité.

Pendant mon stage, j’ai travaillé dans un environnement Linux et j’ai pu voir comment se fait le déploiement avec Docker. Cela m’a donné envie de migrer mon projet sur Ubuntu avec Docker.

Pour Docker, j’ai configuré deux fichiers principaux : docker-compose.yml et Dockerfile.

Le docker-compose.yml définit tous les services dont mon application a besoin : PHP, MySQL, Nginx… et leur réseau pour communiquer entre eux. L’avantage, c’est que chaque conteneur est indépendant et peut être reconstruit facilement avec la commande docker compose up --build.

Le Dockerfile est un script qui s’exécute quand on crée le conteneur. Il installe toutes les dépendances, Composer, Symfony CLI, définit le répertoire de travail, copie les fichiers du projet et expose le port pour que l’application soit accessible.

Grâce à ces deux fichiers, je peux lancer l’application sur n’importe quelle machine avec Docker, et l’environnement reste toujours identique, stable et prêt pour la production.

Pour la mise en production, j’ai utilisé un VPS Ubuntu avec Nginx. Il reçoit les requêtes HTTP et HTTPS, les redirige vers Docker, et gère le SSL pour sécuriser le site. Les informations sensibles sont stockées dans un fichier .env, exclu du dépôt Git pour garantir la sécurité.

Enfin, pour faciliter la prise en main, j’ai rédigé un README.md avec les étapes pour lancer le projet et les commandes utiles, et ajouté un Makefile pour simplifier l’exécution des commandes répétitives.

8. Roadmap (1 min)

Pour la suite :

Connexion sécurisée avec rôles

Historique des prêts par famille

Recherche avancée

QR code pour enregistrer les livres plus rapidement

9. Conclusion (3 min)

Ce projet m’a permis de mettre en pratique mes compétences en développement web et d’apprendre à résoudre des problèmes techniques.
Pendant mon stage, j’ai découvert le développement professionnel avec des tâches variées : pagination React, import CSV, Keycloak, middleware Laravel, tri dans React…

Pour l’avenir de Tosho :

Gestion complète de la bibliothèque

Interface multilingue, planning des bénévoles, alertes pour retours en retard, réservation en ligne.

Sur le plan professionnel :

Je souhaite continuer mes études en alternance pour approfondir mes compétences en programmation et découvrir le DevOps.

Je compte aussi reprendre le rôle de responsable IT de l’association pour la refonte du site vitrine.

En résumé, ce projet m’a permis de renforcer mes compétences, gagner en autonomie et préparer mes prochaines étapes professionnelles.