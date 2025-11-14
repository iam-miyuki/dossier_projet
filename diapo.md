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

<img src="img/outils.png" width="45%" />


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
<img src="img/ui/icons.png" width="32%" style="object-fit: contain;" />

### Identité visuelle ludique conviviale et accessible pour des parents bénévoles non techniques

---

# Arborescence
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

---
# Arborescence
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

---
# Arborescence
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

---
# Arborescence
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

---

# Stack technique
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>



---

# Architechture MVC
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>



---

# Modèle de donnés
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>



---

# Développement

## Front-end

### Mise en place des onglets
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


---

# Développement

## Front-end

### Stimulus
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


---


# Développement
## Back-end
<br><br>
<br><br>
<br><br>
<br>
<br><br>
<br> 

---

# Sécurité
## Gestion d'accès
<br>
<br><br>
<br><br>
<br><br>
<br>
<br>
<br>

---
# Sécurité
## Protection des donnés
<br><br>
<br><br>
<br>
<br>
---


# Déploiement

## Configuration Docker

---
# Déploiement
## Mise en production & Documentation<br>
<br><br>
<br>
<br>
<br>
<br>
<br><br>
<br>

---

# Difficultés rencontrés

## Problème de récupération des données dû au Lazy Loading
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


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




