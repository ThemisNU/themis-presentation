# Themis Lua Lib

![Version](https://img.shields.io/badge/Version-0.1.0--alpha.1-blue.svg)
![Lua](https://img.shields.io/badge/Lua-5.4%2B-blue.svg)

© 2025 BOYER David et COZE Sébastien. All rights reserved. This API is protected by copyright laws. See the LICENSE file for more information.

Welcome to Themis Lua Lib! This project is used to communicate with the Themis App.

## Create a user

```lua
require("themis_lib/models/user")

local User = User:new("
    "Bob158",               -- Username
    "123456",               -- Password
    "bob.dupond@email.fr"   -- E-mail
    "688020529340481571"    -- Discord ID (nullable)
)
```
