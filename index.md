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
### GetDirectoryFiles
```lua
-- Return value: String[]
-- Argument 1: Path of directory (String) Note: Directory path should be formatted like "C:\\GameHackingTools\\"
GetDirectoryFiles(path); -- Returns the file path to each file found in the specified directory.
```

### GetSubdirectories
```lua
-- Return value: String[]
-- Argument 1: Path of directory (String) Note: Directory path should be formatted like "C:\\GameHackingTools\\"
GetSubdirectories(path); -- Returns the path to each subdirectory found in the specified directory.
```

### ReadFile
```lua
-- Return value: String
-- Argument 1: Path of file to read (String)
ReadFile(path); -- Returns the entire contents of the specified file.
```

### WriteFile
```lua
-- Return value: Null
-- Argument 1: Path of file to write (String)
-- Argument 2: The content write (String)
-- Argument 3: OPTIONAL: Whether to append rather than overwrite (Boolean)
WriteFile(path, content[, append]); -- Writes the file content to the specified file.
```

### Toolkit_GetDirectory
```lua
-- Return value: String
Toolkit_GetDirectory(); -- Returns the GameHackingTools Launcher directory.

-- Available Aliases:
GetFireHackDirectory();
GetToolkitDirectory();
```

### GetWoWDirectory
```lua
-- Return value: String
GetWoWDirectory(); -- Returns the game client directory.
```

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
We do not currently have a public API for our interface



## Enums

### Hacks (todo)
Depending on the licence for the currently authenticated user you will get one of the following lists for hacks:

#### Lite
```lua
Hacks = {
  AntiAFK = "Anti-AFK"
}
```

#### Premium ![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
Hacks = {
  AntiAFK = "Anti-AFK",
  StopFall = "Stop Fall"
}
```

### ObjectType

```lua
ObjectType = { 
  Object = 0, 
  Item = 1, 
  Container = 2, 
  Unit = 3, 
  Player = 4, 
  GameObject = 5, 
  DynamicObject = 6, 
  Corpse = 7, 
  AreaTrigger = 8, 
  SceneObject = 9, 
  Conversation = 10
}
```

### MemoryType

```lua
MemoryType = {
  Bool = 0,
  Char = 1,
  Byte = 2,
  Short = 3,
  UShort = 4,
  Int = 5,
  UInt = 6,
  Long = 7,
  ULong = 8,
  Float = 9,
  Double = 10,
  String = 11,
  IntPtr = 12,
  UIntPtr = 13,
  GUID = 14
}
```

### HitFlags

```lua
HitFlags = {
  DoodadCollision = 0x1,
  DoodadRender = 0x2,
  WmoCollision = 0x10,
  WmoRender = 0x20,
  Terrain = 0x100,
  Liquid = 0x20000,
  Cull = 0x80000,
  EntityCollision = 0x100000,
  EntityRender = 0x200000,
  LineOfSight = 0x100111,
  SpellLoS = 0x100010 
}
```
