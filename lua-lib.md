---
layout: default
title: Lua Lib | Themis
---

# 📚 Themis Lua Lib

![Version](https://img.shields.io/badge/Version-0.1.0--beta.1-blue.svg)
![Lua](https://img.shields.io/badge/Lua-5.4%2B-blue.svg)

Themis Lua Lib est la libraire Lua qui vous permettra de gérer les accès des personnages et des utilisateurs, **sans intervention manuelle**. Ainsi, chaque joueur a un compte et ses personnages sur la plateforme Themis.

## 👤 Création d'un utilisateur

A la première connection d'un utilisateur sur le serveur, ce-dit utilisateur devra être enregistré sur Themis. Cela peut se faire, par exemple, via une interface en jeu.

- Le nom d'utilisateur devra **être unique**. Une erreur vous sera retourné si ce n'est pas le cas.
- L'adresse mail devra **être unique**. Une erreur vous sera retourné si ce n'est pas le cas.
- L'identifiant discord n'est pas obligatoire. Néanmoins, sans celui-ci, vous ne pourez pas créer de personnage avec cet utilisateur.

⚠️ En respect au RGPD et à la LIL, vous devez donner la possibilité à l'utilisateur de se rendre sur Themis (via un lien, par exemple).

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Create the user instance.
    local user = Themis.User:new(
        "Bob125",               -- Username
        "Secretpassword",       -- Password
        "bob@example.com",      -- Email
        "332514331516207105"    -- Discord ID (optional but recommended)
    )
    -- Create the user into the Themis Website.
    Themis.User:create(
        user,
        function(success, user)
            if success then
                print("User id:", user.id)
                -- You can work with the new user here.
            else
                print("Failed to create user.")
            end
        end
    )
else
    print("Themis is not accessible.")
end
```

## 👥 Création d'un personnage

A la création d'un personnage sur le serveur, ce-dit personnage devra être enregistré sur Themis.

Le numéro de téléphone n'est pas obligatoire.

⚠️ Il ne peut y avoir plusieurs personnages avec la même prénom, nom et date de naissance en simultané. 

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Create the character instance.
    local character = Themis.Character:new(
        5,                      -- User ID
        "Bob",                  -- Firstname
        "Dupond",               -- Lastname
        "1989-08-12",           -- Birthdate
        "Nice",                 -- Birthplace
        "0658789887"            -- Phone number (optional)
    )
    -- Create the character into the Themis Website.
    Themis.Character:create(
        character,
        function(success, character)
            if success then
                print("Character id:", character.id)
                -- You can work with the new character here.
            else
                print("Failed to create character.")
            end
        end
    )
else
    print("Themis is not accessible.")
end
```

## 🚗 Création d'un permis de conduire

Lorsqu'un personnage obtient son permis, ce-dit permis devra être enregistré sur Themis.

```lua
local Themis = exports['themis']:getThemis()
if Themis then
    -- Create the driving license instance.
    local driving_license = Themis.DrivingLicense:new(
        1,                      -- Character ID
        "active"                -- Status (suspended | active | annuled)
    )
    -- Create the driving license into the Themis Website.
    Themis.DrivingLicense:create(
        driving_license,
        function(success, driving_license)
            if success then
                print("Driving license id:", driving_license.id)
                -- You can work with the new driving license here.
            else
                print("Failed to create driving license.")
            end
        end
    )
else
    print("Themis is not accessible.")
end
```

## 📈 Évolutions futures

~~✅ Enregistrement automatique du permis de conduire~~

✅ Enregistrement automatique des véhicules

✅ Enregistrement automatique des armes

✅ Obtention, à la demande, des informations d'un utilisateur.

✅ Obtention automatique des convocations lors de la connexion du personnage
