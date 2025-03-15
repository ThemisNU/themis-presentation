# Themis Lua Lib

![Version](https://img.shields.io/badge/Version-0.1.0--alpha.1-blue.svg)
![Lua](https://img.shields.io/badge/Lua-5.4%2B-blue.svg)

© 2025 BOYER David et COZE Sébastien. All rights reserved. This API is protected by copyright laws. See the LICENSE file for more information.

Welcome to Themis Lua Lib! This project is used to communicate with the Themis App.

## Create a user

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

## Create a character

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

## Get a specific user

### By id

```lua
require("themis_lib/models/user")

local user = User.getById(589)
```

### By discord id

```lua
require("themis_lib/models/user")

local user = User.getById("688020529340481571")
```

### By username

```lua
require("themis_lib/models/user")

local user = User.getById("Bob158")
```

## Get the characters of a specific user

```lua
require("themis_lib/models/character")

local characters = Character.getByUserId(589)
```
