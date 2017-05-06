## Welcome to wToolkit64 LuaAPI
The aim on the github page is to give you an easy to understand documentation of our extended LuaAPI. This API is bolted onto the ingame lua and all the functions can be called in the usual way.

If there is a function you would like adding please submit a Feature Request [on our community forum](https://gamehacking.tools/community/forum/9-requests/)


## Active Player
### StopFalling ![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
-- Return value: Null
StopFalling(); -- Instantly stops the player falling, Fall damage is calculated as if you landed on a hard surface.
```
### GetMaximumClimbAngle ![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
-- Return value: Int
GetMaximumClimbAngle(); -- Returns the maximum angle(in degrees) the player can walk up.
```

### SendMovementUpdate ![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
-- Return value: Null
SendMovementUpdate(); -- Send a Heartbeat packet to the server. This is useful to update player rotation.
```

### FaceDirection
```lua
-- Return value: Null
-- Argument 1: Radian value of the direction to face
FaceDirection(radians); -- Sets the player rotation to the specified radian. Manual movement or SendMovementUpdate() is required to notify the server of this change.
```

### MoveTo
```lua
-- Return value: Null
-- Argument 1: X Coordinate (float)
-- Argument 2: Y Coordinate (float)
-- Argument 3: Z Coordinate (float)
MoveTo(X, Y, Z); -- Uses ClickToMove to move the player to the specified coordinates
```

## Object 

## Object Manager

## Unit 

## World 

## Hacks 

## File 

## Scripts 

## Miscellaneous 

### Toolkit_GetVersion
```lua
-- Return value: String
Toolkit_GetVersion(); -- Returns the current wToolkit version

-- Available Aliases:
GetFireHackVersion();
GetToolkitVersion();
```

### TerminateClient
```lua
-- Return value: None - Won't return
TerminateClient(); -- Kills the game process
```

### OpenURL
```lua
-- Return value: Null
-- Argument 1: The URL you would like to open (String)
OpenURL(url); -- Opens a webpage using the defaut browser.
```

### IsForeground
```lua
-- Return value: Int
IsForeground(); -- Returns 1 if the game client is the foremost window.
```

### IsHackEnabled
```lua
-- Return value: Int
-- Argument 1: The name of the hack you wish to check the enabled status for (String)
IsHackEnabled(name); -- Returns 1 if the specified hack is enabled.
```

### SetHackEnabled
```lua
-- Return value: Null
-- Argument 1: The name of the hack you wish to check the enabled status for (String)
-- Argument 2: True/False(Boolean)
SetHackEnabled(name, bool); -- Enables or Disables the specified
```


## Interface

## Enums

### Hacks
Depending on the licence for the currently authenticated user you will get one of two lists:

```lua
Hacks = {
  AntiAFK = "Anti-AFK"
}
```

![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
Hacks = {
  AntiAFK = "Anti-AFK",
  StopFall = "Stop Fall"
}
```
