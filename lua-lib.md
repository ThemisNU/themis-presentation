# 📚 Themis Lua Lib

![Version](https://img.shields.io/badge/Version-0.1.0--alpha.1-blue.svg)
![Lua](https://img.shields.io/badge/Lua-5.4%2B-blue.svg)

Themis Lua Lib est la libraire Lua qui vous permettra de gérer les accès des personnages et des utilisateurs, **sans intervention manuelle**. Ainsi, chaque joueur a un compte et ses personnages sur la plateforme Themis.

## 👤 Création d'un utilisateur

A la première connection d'un utilisateur sur le serveur, ce-dit utilisateur devra être enregistré sur Themis. Cela peut se faire, par exemple, via une interface en jeu.

- Le nom d'utilisateur devra **être unique**. Une erreur vous sera retourné si ce n'est pas le cas.
- L'adresse mail devra **être unique**. Une erreur vous sera retourné si ce n'est pas le cas.
- L'identifiant discord n'est pas obligatoire. Néanmoins, sans celui-ci, vous ne pourez pas créer de personnage avec cet utilisateur.

⚠️ En respect au RGPD et à la LIL, vous devez donner la possibilité à l'utilisateur de se rendre sur Themis (via un lien, par exemple).

```lua
require("themis_lib/models/user")

-- Create the user instance.
local user = User:new("
    "Bob158",               -- Username
    "123456",               -- Password
    "bob.dupond@email.fr"   -- E-mail
    "688020529340481571"    -- Discord ID (nullable)
)

-- Create the user into the Themis Website.
user:create()
```

## 👥 Création d'un personnage

A la création d'un personnage sur le serveur, ce-dit personnage devra être enregistré sur Themis.

L'ensemble des informations (prénom, name et date de naissance) sont **obligatoire**.

⚠️ Il ne peut y avoir plusieurs personnages avec la même prénom, nom et date de naissance en simultané. 

```lua
require("themis_lib/models/user")
require("themis_lib/models/character")

-- Get the current user by this discord id. You can also get by id and by username.
local current_user = User.getByDiscordId("688020529340481571")

-- Create the user instance.
local character = Character:new("
    current_user.id,        -- Current user ID
    "Loïc",                 -- Firstname
    "Dubois"                -- Lastname
    "1987-12-25"            -- Birthdate (YYYY-mm-dd)
)

-- Create the character into the Themis Website.
character:create()
```

## 📈 Évolutions futures

✅ Enregistrement automatique du permis de conduire

✅ Enregistrement automatique des véhicules

✅ Enregistrement automatique des armes

✅ Obtention automatique des convocations lors de la connexion du personnage
