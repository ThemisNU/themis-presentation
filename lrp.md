---
layout: default
title: LRP | Themis
---

# 📋 **LRP** - Logiciel de Rédaction de Procédures

## 🔍 **Présentation**  

Le **LRP** (Logiciel de Rédaction de Procédures) est un outil dédié aux agents assermentés (à partir du grade **Agent de Police Judiciaire** - APJ) qui leur permet de rédiger et de gérer des procédures totalement automatisées. Cette fonctionnalité est essentielle pour assurer la conformité et l'efficacité des processus judiciaires, en intégrant des données fiables et actualisées en temps réel. 

L'objectif principal de **LRP** est d'optimiser la rédaction des procédures légales, en garantissant que les documents générés soient précis, clairs et conformes. Chaque procédure est automatiquement assignée à un numéro unique, facilitant ainsi son suivi.

---

## 🛠️ **Utilisation**  

### 📂 **Créer une procédure**  
Lorsque le personnage actif de l'utilisateur est au minimum **Agent de Police Judiciaire (APJ)**, il peut accéder à la fonctionnalité **"Créer une procédure"**. À ce stade, plusieurs types de procédures peuvent être sélectionnés :

- **Interpellation**
- **Plainte**
- *(d'autres types viendront avec les mises à jour futures...)*

Une fois la procédure choisie, un numéro de procédure est automatiquement généré au format :  
`SERVICE | PROCEDURE_ID/ANNEE_DE_CREATION`, par exemple :  
`GN | 1/2025`

### 📋 **Création des documents en fonction du type de procédure**  

#### 1. **Procédure d'Interpellation**  
- L'**APJ** peut uniquement créer et éditer le **PVI** (Procès-Verbal d'Interpellation), et peut le modifier à volonté tant qu'un **OPJ** n'a pas soumis le **PVG** (Procès-Verbal de Garde à Vue).  
- Une fois le PVI créé, un bouton **"Voir le PVI"** s'affiche, permettant à l'APJ de consulter et télécharger le PVI généré en format PDF.  
- Les **PVG** et autres documents judiciaires ne peuvent être créés que par un **OPJ**.

#### 2. **Procédure de Plainte**  
- Cette fonctionnalité est en cours de développement. Le principe sera similaire à la procédure d'interpellation, mais au lieu du PVI/PVG, l'utilisateur sera amené à réaliser une **audition libre** ou une **audition de victime/témoin**, selon le type de plainte.  
- Plus de détails seront ajoutés lors des futures mises à jour.

---

## 🖼️ **Exemples d'images**  

Voici quelques exemples visuels pour illustrer les différentes étapes de la création d'une procédure d'interpellation :  

### 1. **Procédure d'Interpellation**  
La personne impliquée dans la procédure est automatiquement affichée dès que le PVI est créé.

![Procédure d'interpellation](https://i.imgur.com/jTbznu1.png)  
*Affichage de la personne impliquée dans la procédure après création du PVI.*

---

### 2. **Procédure d'Interpellation - PVI**  
L'**APJ** peut consulter et télécharger le PVI une fois qu'il est généré.

![Procédure d'interpellation - PVI](https://i.imgur.com/CivKZJa.png)  
*Exemple de Procédure d'Interpellation - PVI.*

---

### 3. **Procédure d'Interpellation - PVG**  
Une fois qu'un **OPJ** soumet le **PVG**, l'**APJ** peut également visualiser ce document.

![Procédure d'interpellation - PVG](https://i.imgur.com/CivKZJa.png)  
*Exemple de Procédure d'Interpellation - PVG.*

---

### 4. **Création du PVI**  
L'interface de création du **PVI** pour l'**APJ**.

![Procédure d'interpellation - Création PVI](https://i.imgur.com/yMQAnM7.png)  
*Création du Procès-Verbal d'Interpellation (PVI).*

---

### 5. **Création du PVG**  
Une fois le PVI soumis, l'**OPJ** peut créer et soumettre le **PVG**.

![Procédure d'interpellation - Création PVG](https://i.imgur.com/nBvuSsQ.png)  
*Création du Procès-Verbal de Garde à Vue (PVG).*

