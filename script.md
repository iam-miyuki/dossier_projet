1. Introduction (30 sec)

Bonjour, je m’appelle Miyuki CHERBAL.
Je viens de Japon, et ça fait 10 ans que je vis en France. J'ai fait mes études en histoire de l'art et j'ai travaillé comme photographe scolaire au japon. Depuis que je suis maman je suis famme au foyer.
Pour quoi j'ai choisi cette formation, parce que je suis entouré des développeurs dans mon entrourage et ca m'a motivée à apprendre ce métier pour un jour comprendre de quoi il parle !

Dans le cadre de ma formation, j'ai réalisé un stage dans une entreprise spécialisée en SEO. Et j'ai participé à un projet en React et en laravel. Cette expérience m’a beaucoup apporté et elle m'a permit d’appliquer des bons pratiques à mon projet personnel, que je vous présente aujourd’hui, Tosho.

2. Présentation du projet (1 min)

Tosho signifie “bibliothèque” ou “livre” en japonais.
C’est une application web de gestion de bibliothéque pour une association dont je fais partie. L'assosiatin propose des cours du japonais aux enfants bilangues franco-japonais. J’ai choisi ce projet parce que je souhaite que ces enfants puissent accéder aux livres en japonais et se familiariser avec leur langue maternelle.

Acutellement, les prêts des livres sont géré par une application web qui a été développé il y longtemps par un ancien parent bénévole. Cette application est fonctionnelle, mais il y a plusieurs limites. Par example, il n’y a pas d’interface admin, ce qui complique la gestion du catalogue, et l’interface n’est pas très intuitive pour les utilisateurs.

3. Objectif et MVP

Donc l'objectif de mon projet est de refaire une application web user-friendly qui facilite la gestion de la bibliothéque.

Pour le MVP, il est nécessaire d’avoir la fonctionnalité de gesion des prêts de livres, et inclure une interface admin.

4. Types et fonctionnalité

Qui sont des utilisateurs de mon application ? Ce sont des parents bénévols de l'association, et il y a deux types de bénévoles. Premimèrement, ce sont des bibliothécaires, qui s’occupent des prêts et des retours de livres, et participent également à la session d’inventaire organisée une fois par an.

Deuxiemement ce sont des admin. En plus des fonctionnalités des bibliothécaires, ils supervisent toute la gestion de la bibliothèque : ils peuvent gérer le catalogue des livres, les comptes des familles emprunteuses, organiser les sessions d’inventaire et gérer les comptes des bibliothécaires. À noter que les comptes des familles emprunteuses sont uniquement créés pour pouvoir assigner chaque prêt à une famille ; ces familles n’ont pas la possibilité de se connecter à l’application.

5. Contrantes

Comme ce sont des parents bénévoles qui utilisent cette application, l’interface doit être intuitive et facile à utiliser.
Il faudra également gérer les droits d’accès selon le rôle des utilisateurs.
Enfin, pour garantir une bonne gestion des prêts de livres, les données doivent être mises à jour en temps réel.

6. Gestion de projet

Dans un premier temps, j’ai commencé par lister toutes les fonctionnalités à développer et j'ai rédigé des userstories en markdown. Comme je suis seule à travailler sur ce projet, j'ai adapté la méthode agile par un simple système de check-liste en markdown pour suivre l'avancement de mon projet.

7. Arborescece

Une fois que j’ai clarifié les besoins, j’ai conçu la structure de mon application.
Après connexion, l’utilisateur arrive sur la page d’accueil correspondant à son rôle.

8. Arborescence admin 1

Les administrateurs ont accès aux pages de gestion des livres et des comptes des familles.
Ils peuvent effectuer ici toutes les opérations CRUD.


9. Arborescence admin 2
Toujours depuis l’interface administrateur, ils ont également accès aux pages de gestion des sessions d’inventaire et des comptes des bibliothécaires qui permet les opération CRUD.

10. Arborescence biblithécaire 1

Ensuite, ici l'interface bibliothécaire. Ils peuvent gérer les prêts de livres en effectuant des recherches  soit par livre, soit par famille emprunteuse, soit par les prêts en retard.

11.  Arborescence biblithécaire 2

Les bibliothécaires peuvent consulter les sessions d’inventaire en cours et y contribuer en ajoutant les livres qu’ils ont vérifiés physiquement. 
Lorsqu’une session d’inventaire est ouverte par un administrateur, les bibliothécaires vérifient la présence de tous les livres de la bibliothèque, et signalent en cas d'absence de livre etc.

12. Wireframes

Ensuite, pour visualiser la structure de mon application, j’ai créé des wireframes sur Figma.
Les wireframes permettent de vérifier la navigation du site et de valider l’organisation des écrans sur mobile et sur desktop.

13. Maquettes

Et pour avoir le rendu final de mon site, j’ai créé des maquettes, toujours sur Figma.
Cette étape permet de faire des choix visuels, notamment pour les couleurs et l’identité graphique.
Il est important d’avoir des maquettes avant l’étape d’intégration en HTML et CSS pour pouvoir se concentrer à coder.

14. Charte graphique

J’ai choisi trois couleurs principales :
Le bleu foncé pour le texte, les bordures et les icônes.
Le violet clair pour l’interface bibliothécaires.
Le bleu clair pour l’interface admin.

Ensuite, j’ai vérifié la bonne lisibilité du texte sur chaque couleur de fond.

15. Charte graphique 2

J’ai conçu le logo de Tosho sur Figma. Ensuite, j’ai choisi d’utiliser des icônes au style pixel art, également disponibles sur Figma, que j’ai exportées au format SVG pour leur scalabilité sur tous les écrans. J’ai choisi les polices pour qu’elles soient en accord avec le logo et les icônes.
J’ai adopté ce style pour que mon application soit ludique, conviviale et accessible, à l’image de l’association

16. Stack technique

Ensuite, la conception technique.
Côté front-end, j’ai utilisé du HTML, CSS, Twig, et JavaScript. Et côté back-end, du PHP avec framework Symfony et Mysql comme SGBD.

J'ai utilisé VSCode comme l'IDE, Git pour le versionning et gitHub pour le dépot distant. J'avais commencé mon projet sous l'environnement windows avec xampp comme serveur web, mais au fur et à mesure, j'ai appercu que xampp était parfois unstable, donc j'ai ensuite changé mon environnement de travail vers WSL ubuntu avec Docker.

17. MVC

Symfony utilise l’architecture MVC, ce qui permet de bien séparer les rôles dans l’application.
Par exemple, lorsqu’un utilisateur veut afficher les informations d’un livre, il envoie une requête au contrôleur.
Le contrôleur demande alors au Modèle de communiquer avec la base de données.
Le Modèle renvoie les données du livre au contrôleur, qui les transmet ensuite à la Vue.
La Vue génère le rendu avec les infos du livre, et le contrôleur renvoie la page à l’utilisateur.
Dans mon application, le Repository joue le rôle de Modèle et Twig celui de la Vue.

18. Modéle de donnés

Pour la base de données, j’ai d’abord conçu le modèle sur papier et je l’ai validé avec mon formateur, pour m’assurer que les tables et leurs relations soient cohérentes avec la logique de mon application. Ensuite, j’ai traduit ces tables en entités en créant des classes PHP, et Doctrine, l’ORM de Symfony, s’est chargé de mapper automatiquement mes entités avec la base de données.

Les relations sont gérées grâce aux clés primaires et aux clés étrangères. Par exemple, ma table loan — qui représente un prêt — est reliée à la table family grâce à une clé étrangère qui vient de la table family. Un prêt est associé à une seule famille, mais une famille peut avoir plusieurs prêts. La cardinalité ici est donc one-to-many


19. Sécurité gestion d'accès

Pour garantir un accès sécurisé à mon application, j’ai configuré ici pour gérer la redirection après la connexion, selon le rôle de l’utilisateur.
Et pour les comptes bibliothécaires, j’ai ajouté une vérification supplémentaire du statut du compte 'activé' ou 'désactivé', grâce à un UserChecker que j’ai configuré.

20. Sécurité d'accès

L’accès aux différentes routes de mes contrôleurs est également sécurisé grâce à isGranted de Symfony.
Côté front, certains éléments d’interface réservés aux admins sont aussi protégés avec isGranted. Par exemple, le bouton qui permet de basculer entre l’interface admin et l’interface bibliothécaire n’est affiché que pour les admins.

En résumé, chaque utilisateur voit et peut faire uniquement ce qui correspond à son rôle

21. Sécurité des données

Symfony utilise l’ORM Doctrine, qui fait le lien entre la base de données et les entités PHP. Et toutes les requêtes vers la base passent par Doctrine.
Avec le QueryBuilder et setParameter, Doctrine sépare les données saisies par l’utilisateur de la requête SQL. Ça signifie que les données des utilisateurs ne sont jamais insérées directement dans le SQL, la requête les traite comme de simples valeurs et non comme des instructions, ce qui protège la base de données contre les injections SQL.

Les formulaires sont protégés par des tokens CSRF. À chaque envoi, Symfony crée un jeton unique pour s’assurer que seul un utilisateur authentifié peut soumettre le formulaire.



22. Front-end 

Maintenant, je voudrais vous présenter quelques fonctionnalités que j’ai développées.

Ici c'est un formulaire d'ajout d'un livre au catalogue. Le formulaire comporte plusieurs champs : le titre, l’auteur, le titre et l’auteur en hiragana — c’est-à-dire en caractères japonais — ainsi qu’un champ pour le lien de la couverture du livre.
Pour faciliter la saisie de ces informations, j’ai mis en place une fonctionnalité de préremplissage automatique à partir du code ISBN.

Alors, comment ai-je fait ? J’ai utilisé des API et Stimulus. Stimulus est un framework JavaScript léger qui permet de rendre uniquement cette partie de l’application en SPA.
Pour l’utiliser, j’ai installé le bundle Stimulus via Composer, ce qui crée un fichier controller.js que j’ai ensuite lié à mon formulaire

23. Front 

Pour récupérer les informations sur le livre, j’ai utilisé deux API : une API japonaise pour obtenir le titre et l’auteur en japonais, et une autre API pour toutes les autres informations.
Ici, je vous montre un exemple pour l’API japonaise. Avec Postman, j’ai vérifié que l’API renvoie un tableau contenant les informations et j’ai identifié les champs qui m’intéressent.

Ensuite, dans mon controller.js, j’ai utilisé async pour accepter la promesse. Cela signifie que même si les informations ne sont pas encore récupérées lors de l’affichage, la page s’affiche quand même sans données, et se met à jour dès que les infos sont disponibles.

Ici, preventDefault() sert à empêcher la soumission du formulaire par défaut.

Ensuite, je récupère l’ISBN saisi par l’utilisateur et je fais une requête fetch() vers une API.

J’attends la réponse et, si l’API ne répond pas, une erreur est affichée dans la console.

Une fois les informations récupérées, je les convertis en JSON et je vérifie comment accéder aux données qui m’intéressent.
Enfin, j’assigne les informations récupérées aux champs du formulaire correspondants.

24. front
Pour lier mon controller.js au formulaire, j’ai ajouté data-controller sur la balise du formulaire.
Ensuite, sur le bouton, j’ai ajouté data-action pour définir quelle méthode doit être déclenchée lorsque l’utilisateur clique dessus.
Ainsi, le formulaire est automatiquement prérempli grâce à l’API


25. Back-end 

Je vous montre maintenant la partie CRUD de mon applicaiton. 
Quand un utilisateur veut prêter un livre à une famille, d'abord il faut que ce livre soit "disponible", et que ce livre n'a pas de prêt en cours. J'ai géré les statuts pour les livres et les prêts avec Enum. L'utilisation des enum permet de faciliter les suivi et éviter de faute de frappe dans le code. 

26. back-end

Chaque prêt est associé à un livre et à une famille emprunteuse grâce à des clés étrangères.
Imaginons maintenant qu’une famille apporte un livre à un bibliothécaire. Le bibliothécaire peut rechercher un prêt soit par famille, soit par livre. Chaque livre de la bibliothèque possède un code unique attribué par l’association. Ici, le bibliothécaire choisit de chercher un prêt par code du livre.


27. back-end
Une fois le formulaire de recherche soumis, le contrôleur demande au BookRepository de chercher un livre avec ce code. S’il n’y a pas de livre correspondant, un message d’erreur est affiché. Si le livre est trouvé, on redirige vers la route show-book avec l’ID du livre.

Sur cette route, on vérifie si le livre a un prêt en cours grâce à une requête personnalisée appelée findWithBookAndStatus. Dans le LoanRepository, on cherche un prêt assigné à ce livre et qui a un statut de prêt « en cours » ou « en retard ».
Si le LoanRepository trouve un résultat, c’est-à-dire que le livre apporté doit être rendu, 


28. back-end

on affiche les informations du livre avec un bouton « rendre ».
Sinon, on affiche un bouton « prêter ce livre ».




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