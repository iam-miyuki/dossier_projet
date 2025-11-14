---
marp: true
paginate: true
_mermaid: true
---

![Texte alternatif](img/ui/logo-big.svg)

**Développé par Miyuki CHERBAL**

---

# Présentation du projet

## **Tosho – Application de gestion de bibliothèque**

- _Tosho_ signifie **« bibliothèque »** ou **« livre »** en japonais
- Projet réalisé pour une **école japonaise associative** dirigée par des **parents bénévoles**
- Application actuelle :
  - Fonctionnalités **limitées**
  - Pas d’**accès administrateur**
  - Interface **simple**, peu **intuitive**

---

# Objectif et MVP

## Objectif

- Faciliter la **gestion des prêts et retours**
- Fournir une **interface administrateur**

## MVP

- **Enregistrer un prêt ou un retour**
- **Rechercher un prêt** par livre ou par famille
- **Interface admin** pour que les bénévoles travaillent en autonomie
- Plus besoin de dépendre du **développeur initial**

---

# Rôles et fonctionnalités

| Type d’utilisateur | Fonctionnalités                                                                                                                                                                                                                                                                                                     |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Bibliothécaire** | - Gérer les **prêts** et **retours** de livres <br> - Participer à une **session d’inventaire**                                                                                                                                                                                                                     |
| **Admin**          | - **Livres** : CRUD <br> - **Familles** : CRUD <br> - **Sessions d’inventaire** : créer, suivre l’avancement, mettre à jour le statut, supprimer <br> - **Bibliothécaires** : créer un compte, envoyer email automatique, activer/désactiver, supprimer <br> - **Supervision** : accès à l’interface bibliothécaire |

---

#  Contraintes

- Interface **simple et intuitive** pour des bénévoles non techniques
- **Gestion des accès** selon le rôle :
  - **Administrateurs** : toutes les fonctionnalités
  - **Bibliothécaires** : prêts et inventaire uniquement
- **Données fiables et en temps réel** pour éviter les doublons et les erreurs d’inventaire

---

# Gestion de projet

- **Liste des fonctionnalités** → Cahier des charges & User stories en Markdown

<div style="display: flex; justify-content: space-around; align-items: center;">
  <img src="img/ui/cahierdescharges.PNG" width="45%" />
  <img src="img/ui/userstoris.PNG" width="45%" />
</div>

---

# Wireframes & Maquettes

## Objectif

- Clarifier la **structure et le parcours utilisateur**
- Vérifier l’**ergonomie** avant le développement

---

## Wireframes – Aperçu

<div style="display: flex; justify-content: space-around; align-items: center;">
<img src="img/ui/Retour.svg" height="700px" />
  <img src="img/ui/wireframe-mb (2).PNG" height="700px" />
</div>

---

## Maquettes Figma – Aperçu

<div style="display: flex; justify-content: space-around; align-items: center;">
  <img src="img/ui/maquette-desk.PNG" width="45%" />
  <img src="img/ui/maquette-mb2.PNG" width="45%" />
</div>

---

# Outils utilisés

<table style="width:100%; text-align:center;">
  <tr>
    <td><img src="img/logos/devicon_git.svg" width="80px" /><br>Git</td>
    <td><img src="img/logos/mdi_github.svg" width="80px" /><br>GitHub</td>
    <td><img src="img/logos/devicon_vscode.svg" width="80px" /><br>VS Code</td>
    <td><img src="img/logos/logos_xampp.svg" width="80px" /><br>XAMPP</td>
    <td><img src="img/logos/logos_ubuntu.svg" width="80px" /><br>WSL Ubuntu</td>
  </tr>
  <tr>
    <td><img src="img/logos/skill-icons_docker.svg" width="80px" /><br>Docker</td>
    <td><img src="img/logos/skill-icons_postman.svg" width="80px" /><br>Postman</td>
    <td><img src="img/logos/devicon_dbeaver.svg" width="80px" /><br>DBeaver</td>
    <td><img src="img/logos/codicon_terminal-git-bash.svg" width="80px" /><br>Git Bash</td>
    <td></td>
  </tr>
</table>

---

# Charte graphique

## Palette de couleurs

<div style="display: flex; justify-content: space-around; align-items: flex-start; gap: 5px;">
  <img src="img/ui/chart.svg" width="32%" style="object-fit: contain;" />
  <img src="img/ui/contrast.PNG" width="33%" style="object-fit: contain;" />
  <img src="img/ui/contrast1.PNG" width="33%" style="object-fit: contain;" />
</div>


---

# Charte graphique
## Logo

<img src="img/ui/logo-big.svg" width="32%" style="object-fit: contain;" />

## Icônes
<div style="display: flex; justify-content: space-around; align-items: flex-start; gap: 20px;">
  <img src="img/ui/child-book.svg" width="10%" style="object-fit: contain;" />
  <img src="img/ui/books.svg" width="10%" style="object-fit: contain;" />
  <img src="img/ui/family.svg" width="10%" style="object-fit: contain;" />
  <img src="img/ui/home.svg" width="10%" style="object-fit: contain;" />
  
</div>

### Identité visuelle ludique conviviale et accessible pour des parents bénévoles non techniques

---

# Arborescence

<img src="img/sitemap.PNG" width="80%"/>

---
# Arborescence
<img src="img/arbbib.PNG" width="100%"/>

---
# Arborescence
<img src="img/admin1.PNG" width="100%"/>

---
# Arborescence
<img src="img/admin2.PNG" width="100%"/>


---

# Stack technique

## Front-end
<table style="width:100%; text-align:center;">
<tr>
    <td><img src="img/logos/logos_html-5.svg" width="80px" /><br>HTML</td>
    <td><img src="img/logos/logos_css-3.svg" width="80px" /><br>CSS</td>
    <td><img src="img/logos/material-icon-theme_twig.svg" width="80px" /><br>Twig</td>
    <td><img src="img/logos/logos_javascript.svg" width="80px" /><br>JavaScript</td>
</tr>
</table>

## Back-end
<table style="width:100%; text-align:center;">
<tr>
    <td><img src="img/logos/devicon_php.svg" width="80px" /><br>PHP 8.2</td>
    <td><img src="img/logos/devicon_symfony.svg" width="80px" /><br>Symfony 6.4</td>
    <td><img src="img/logos/logos_mysql.svg" width="80px" /><br>MySQL</td>
</tr>
</table>

---

# Architechture MVC


<img src="img/markdown-image-86221.png" width="80%"/>

---

# Modèle de donnés

<img src="img/toshomdc.png" width="80%"/>

---

# Développement

## Front-end

### Mise en place des onglets
<div style="display: flex; justify-content: space-around; align-items: flex-start; gap: 5px;">
<img src="img/code-diapo/onglets-twig.svg" width="40%"/>
*loan/index.html.tiwg*
<img src="img/code-diapo/css-tab.svg" width="40%"/>
*_tabs.css*
<img src="img/code-diapo/tab-controller.svg" width="40%"/>
*LoanController.php*

</div>

---

# Développement

## Front-end

### Stimulus


---


# Développement
## Back-end

### 

---

# Sécurité
## Gestion d'accès

---
# Sécurité
## Protection des donnés

---


# Déploiement

## Configuration Docker

---
# Déploiement
## Mise en production & Documentation

---

# Difficultés rencontrés

## Problème de récupération des donnés dû à Lazy Roading

---

# Démo

---

# Conclusion

- **Mise en pratique des compétences web**  
  HTML, CSS, JS, PHP, Symfony, intégration fidèle aux maquettes

- **Résolution de problèmes techniques**  
  Débogage, optimisation, interactions dynamiques

- **Vision complète du cycle de développement**  
  Analyse des besoins → conception → développement → tests → optimisation
---

# Roadmap

- **Perspectives et projet pro**  
  - Tosho utilisé en conditions réelles par l’association
  - Refonte de site de l'asso en VueJs
  - Alternance

- **Évolutions futures**  
  - Recherche interactive AJAX  
  - Interface multilingue FR / JP  
  - Planning parents-bibliothécaires  
  - Réservation en ligne




