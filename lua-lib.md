---
layout: default
title: Lua Lib | Themis
---

# 📚 Themis Lua Lib

![Version](https://img.shields.io/badge/Version-0.1.0--beta.2-blue.svg)
![Lua](https://img.shields.io/badge/Lua-5.4%2B-blue.svg)

© 2025 BOYER David et COZE Sébastien. Tous droits réservés. Cette API est protégée par les lois sur le droit d'auteur. Consultez le fichier LICENSE pour plus d'informations.

Themis Bibliothèque Lua est la bibliothèque Lua qui vous permet de gérer l'accès des personnages et des utilisateurs **sans intervention manuelle**. Chaque joueur dispose d'un compte et de ses personnages sur la plateforme Themis.

## 💼 ESX

Si vous utilisez le framework ESX, la création des utilisateurs, des personnages et des permis se fait automatiquement.

## 👤 Créer un utilisateur

Lorsqu'un utilisateur se connecte au serveur pour la première fois, il doit être enregistré sur Themis. Cela peut être fait, par exemple, via une interface en jeu.

- Le nom d'utilisateur doit **être unique**. Une erreur sera retournée s'il ne l'est pas.
- L'adresse e-mail doit **être unique**. Une erreur sera retournée si elle ne l'est pas.
- L'ID Discord n'est pas obligatoire. Cependant, sans lui, vous ne pourrez pas créer de personnage pour cet utilisateur.

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Créer une instance utilisateur.
    local user = Themis.User:new(
        "Bob125",               -- Nom d'utilisateur
        "MotdepasseSecret",     -- Mot de passe
        "bob@example.com",      -- E-mail
        "332514331516207105"    -- ID Discord (optionnel mais recommandé)
    )
    -- Créer l'utilisateur sur le site Themis.
    Themis.User:create(
        user,
        function(success, user)
            if success then
                print("ID utilisateur :", user.id)
                -- Vous pouvez travailler avec le nouvel utilisateur ici.
            else
                print("Échec de la création de l'utilisateur.")
            end
        end
    )
else
    print("Themis n'est pas accessible.")
end
```

## 👥 Créer un personnage

Lors de la création d'un personnage sur le serveur, le personnage doit être enregistré sur Themis.

Le numéro de téléphone n'est pas obligatoire.

⚠️ Il ne peut pas y avoir plusieurs personnages avec le même prénom, nom et date de naissance simultanément.

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Créer une instance de personnage.
    local character = Themis.Character:new(
        5,                      -- ID utilisateur
        "Bob",                  -- Prénom
        "Dupond",               -- Nom
        "1989-08-12",           -- Date de naissance
        "Nice",                 -- Lieu de naissance
        "0658789887"            -- Numéro de téléphone (optionnel)
    )
    -- Créer le personnage sur le site Themis.
    Themis.Character:create(
        character,
        function(success, character)
            if success then
                print("ID personnage :", character.id)
                -- Vous pouvez travailler avec le nouveau personnage ici.
            else
                print("Échec de la création du personnage.")
            end
        end
    )
else
    print("Themis n'est pas accessible.")
end
```

## 🚗 Créer un permis de conduire

Lorsqu'un personnage obtient son permis de conduire, le permis doit être enregistré sur Themis.

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Créer une instance de permis de conduire.
    local driving_license = Themis.DrivingLicense:new(
        1,                      -- ID personnage
        "active"                -- Statut (suspended | active | annuled)
    )
    -- Créer le permis de conduire sur le site Themis.
    Themis.DrivingLicense:create(
        driving_license,
        function(success, driving_license)
            if success then
                print("ID permis de conduire :", driving_license.id)
                -- Vous pouvez travailler avec le nouveau permis ici.
            else
                print("Échec de la création du permis de conduire.")
            end
        end
    )
else
    print("Themis n'est pas accessible.")
end
```

## 🔫 Créer une arme

Lorsqu'un personnage obtient légalement une arme, celle-ci doit être enregistrée sur Themis.

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Créer une instance d'arme.
    local weapon = Themis.Weapon:new(
        2,                      -- ID personnage
        1,                      -- ID agent
        "Carabine",             -- Type d'arme
        "Browning Bar Mk3",     -- Modèle d'arme
        ".243 Winchester",      -- Calibre de l'arme
        "ADDF2036ERY",          -- Numéro de série
        "2023-10-01"            -- Date d'acquisition (optionnelle, aujourd'hui par défaut)
    )
    -- Créer l'arme sur le site Themis.
    Themis.Weapon:create(
        weapon,
        function(success, weapon)
            if success then
                print("ID arme :", weapon.id)
                -- Vous pouvez travailler avec la nouvelle arme ici.
            else
                print("Échec de la création de l'arme.")
            end
        end
    )
else
    print("Themis n'est pas accessible.")
end
```

## 👤 Obtenir un utilisateur spécifique

⚠️ Supprimé depuis la version v0.1.0-beta.1

### Par ID

```lua
require("themis_lib/models/user")

local user = User.getById(589)
```

### Par ID Discord

```lua
require("themis_lib/models/user")

local user = User.getById("688020529340481571")
```

### Par nom d'utilisateur

```lua
require("themis_lib/models/user")

local user = User.getById("Bob158")
```

## 👥 Obtenir les personnages d'un utilisateur spécifique

⚠️ Supprimé depuis la version v0.1.0-beta.1

```lua
require("themis_lib/models/character")

local characters = Character.getByUserId(589)
```

## 📈 Évolutions futures

~~✅ Enregistrement automatique des permis de conduire~~  

✅ Enregistrement automatique des véhicules  

~~✅ Enregistrement automatique des armes~~  

✅ Récupération des informations utilisateur à la demande  

✅ Récupération automatique des convocations lorsque le personnage se connecte  
✅ Récupération des informations utilisateur à la demande  

✅ Récupération automatique des convocations lorsque le personnage se connecte  
