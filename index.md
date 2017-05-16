## Welcome to wToolkit64 LuaAPI
The aim on the github page is to give you an easy to understand documentation of our extended LuaAPI. This API is bolted onto the ingame lua and all the functions can be called in the usual way.

If there is a function you would like adding please submit a Feature Request [on our community forum](https://gamehacking.tools/community/forum/9-requests/)


----------------------------------------------------
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

### FaceDirection
```lua
-- Return value: Null
-- Argument 1: Radian value of the direction to face
FaceDirection(radians); -- Sets the player rotation to the specified radian. Manual movement or SendMovementUpdate() is required to notify the server of this change.
```

----------------------------------------------------
## Object Manager
### GetObjectCount
```lua
-- Return value: Int
GetObjectCount(); -- Get the number of objects in the object manager.
```

### GetObjectWithIndex
```lua
-- Return value: The Object
-- Argument 1: Object Index (Int)
GetObjectWithIndex(index); -- Get an object in the object manager from using its index

-- Available Aliases:
GetObjectFromIndex();
```

### GetLocalPlayer
```lua
-- Return value: The Player Object
GetLocalPlayer(); --  Get the player to use used with object manager functions

-- Available Aliases:
CurrentPlayer();
```

### GetLocalTarget
```lua
-- Return value: The Target Object
GetLocalTarget(); --  Get the players target as an object to use used with object manager functions

-- Available Aliases:
PlayerTarget();
CurrentTarget();
```

----------------------------------------------------
## Object 
### ObjectName
```lua
-- Return value: String
-- Argument 1: The Object
ObjectName(object); --  Get the objects name from the Object Manager
```

### ObjectGUID
```lua
-- Return value: String
-- Argument 1: The Object
ObjectGUID(object); --  Get the objects GUID from the Object Manager
```

### ObjectScale
```lua
-- Return value: Int
-- Argument 1: The Object
ObjectScale(object); --  Get the objects scale
```

### ObjectExists
```lua
-- Return value: Int
-- Argument 1: The Object
ObjectExists(object); --  Returns 1 if the specified objects still exists in the Object Manager
```

### ObjectPosition
```lua
-- Return value: X,Y,Z (float)
-- Argument 1: The Object
ObjectPosition(object); --  Returns the in game coordinates for the specifed object.
```

### ObjectFacing
```lua
-- Return value: float
-- Argument 1: The Object
ObjectFacing(object); --  Returns the direction the object is facing
```

### ObjectTypeFlags
```lua
-- Return value: Int (ObjectType)
-- Argument 1: The Object
ObjectTypeFlags(object); --  Returns the type of the object
```

### ObjectTypeMask
```lua
-- Return value: Int 
-- Argument 1: The Object
ObjectTypeMask(object); --  Returns the typemask of the object
```

### ObjectInteract
```lua
-- Return value: Null 
-- Argument 1: The Object
ObjectInteract(object); --  Interacts the the specifed object

-- Available Aliases:
ObjectRightClick();
InteractWith();
```

### GetDistanceBetweenObjects
```lua
-- Return value: Float 
-- Argument 1: Object A
-- Argument 2: Object B
GetDistanceBetweenObjects(objectA, objectB); --  Returns the 3D distance between the specified objects
```

### GetAnglesBetweenObjects
```lua
-- Return value: Float 
-- Argument 1: Object A
-- Argument 2: Object B
GetAnglesBetweenObjects(objectA, objectB); --  Returns the angle between the specified objects

-- Available Aliases:
GetAngleBetweenObjects();
```

### GetPositionBetweenObjects
```lua
-- Return value: X,Y,Z (float) 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: Distance away from Object B
GetPositionBetweenObjects(objectA, objectB, dist); --  Returns X,Y,Z coordinates that are the specified distance away from Object B
```

### ObjectIsFacing
```lua
-- Return value: Int 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float)
ObjectIsFacing(objectA, objectB[, marginOfError]); --  Get whether an object is facing another.
```

### ObjectIsBehind
```lua
-- Return value: Int 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float)
ObjectIsBehind(objectA, objectB[, marginOfError]); --  Get whether an object is behind another.
```

### ObjectIsInfront
```lua
-- Return value: Int 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float)
ObjectIsInfront(objectA, objectB[, marginOfError]); --  Get whether an object is infront of another.
```

### ObjectIsType
```lua
-- Return value: Int 
-- Argument 1: Object
-- Argument 2: ObjectType
ObjectIsType(object, objectType); --  Returns 1 if the object if the specified type
```

### ObjectField
```lua
-- Return value: As Specified 
-- Argument 1: Object
-- Argument 2: Offset to read (Int)
-- Argument 2: MemoryType
ObjectField(object, offset, memoryType); --  Returns the value at the specifed memory

-- Available Aliases:
ObjectMemory();
```

### ObjectDescriptor
```lua
-- Return value: As Specified 
-- Argument 1: Object
-- Argument 2: Descriptor to read (Int)
-- Argument 2: MemoryType
ObjectDescriptor(object, offset, memoryType); --  Returns the value at the specifed descriptor
```

----------------------------------------------------
## Unit 
We do not currently have a public API this section

----------------------------------------------------
## World 
### TraceLine
```lua
-- Return value: The X, Y, and Z coordinates of the hit position, or nil, nil, nil if nothing was hit 
-- Argument 1: The starting X coordinat (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: The ending X coordinate (float)
-- Argument 5: The ending Y coordinate (float)
-- Argument 6: The ending Z coordinate (float)
-- Argument 7: One or more members of the HitFlags table combined with bit.bor
TraceLine(StartX, StartY, StartZ, EndX, EndY, EndZ, Flags); -- Perform a raycast between two positions.

-- Available Aliases:
Traceline();
WorldFrame_Intersect();
Raycast();
```

### GetCameraPosition
```lua
-- Return value: The X, Y, and Z coordinates of the camera
GetCameraPosition(); -- Get the camera position.
```

----------------------------------------------------
## Hacks 
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

----------------------------------------------------
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
----------------------------------------------------
## Scripts 
We do not currently have a public API this section

----------------------------------------------------
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

----------------------------------------------------
## Interface
We do not currently have a public API this section


----------------------------------------------------
## Enums

### Hacks (todo)
Depending on the licence for the currently authenticated user you will get one of the following lists for hacks:

#### Lite
```lua
Hacks = {
  Anti-AFK = "Anti-AFK",
  DisplayAllLevels = "Display All Levels",
  DrunkPercent = "DrunkPercent",
  FieldofView = "Field of View",
  FollowAnyone = "Follow Anyone",
  LuaUnlock = "Lua Unlock",
  MorphDisplayId = "Morph DisplayId",
  MorphDisplayId = "Morph DisplayId",
  MorphGender = "Morph Gender",
  MorphItemSlot = "Morph Item Slot",
  MorphRace = "Morph Race"
}
```

#### Premium ![PremiumOnly](https://gamehacking.tools/api/premiumbadge.jpg)
```lua
Hacks = {
  Airwalk = "Airwalk",
  Anti-AFK = "Anti-AFK",
  CollisionRenderer = "Collision Renderer",
  DisplayAllLevels = "Display All Levels",
  DoodadCollision = "Doodad Collision",
  DoodadRenderer = "Doodad Renderer",
  DrunkPercent = "DrunkPercent",
  FacingCast = "Facing Cast",
  FieldofView = "Field of View",
  FollowAnyone = "Follow Anyone",
  LiquidRenderer = "Liquid Renderer",
  LuaUnlock = "Lua Unlock",
  MorphDisplayId = "Morph DisplayId",
  MorphDisplayId = "Morph DisplayId",
  MorphGender = "Morph Gender",
  MorphItemSlot = "Morph Item Slot",
  MorphRace = "Morph Race",
  MountedLoot = "Mounted Loot",
  MovingLoot = "Moving Loot",
  NoSwimming = "No Swimming",
  NoKnockback = "NoKnockback",
  ObscureTarget = "Obscure Target",
  SpectateCollision = "Spectate Collision",
  SpectateFreeRoam = "Spectate Free Roam",
  SpectatePosition = "Spectate Position",
  SpectateSpeed = "Spectate Speed",
  TerrainCollision = "Terrain Collision",
  TerrainRenderer = "Terrain Renderer",
  TrackBeasts = "Track Beasts",
  TrackByName = "Track ByName",
  TrackCritters = "Track Critters",
  TrackDemons = "Track Demons",
  TrackDragons = "Track Dragons",
  TrackElementals = "Track Elementals",
  TrackFishing = "Track Fishing",
  TrackGasClouds = "Track Gas Clouds",
  TrackGiants = "Track Giants",
  TrackHerbs = "Track Herbs",
  TrackHumanoids = "Track Humanoids",
  TrackInscription = "Track Inscription",
  TrackLockpicking = "Track Lockpicking",
  TrackMachines = "Track Machines",
  TrackMinerals = "Track Minerals",
  TrackNon-CombatPets = "Track Non-Combat Pets",
  TrackOpenable = "Track Openable",
  TrackPVPObjects = "Track PVP Objects",
  TrackSlimes = "Track Slimes",
  TrackTotems = "Track Totems",
  TrackTraps = "Track Traps",
  TrackTreasure = "Track Treasure",
  TrackUndead = "Track Undead",
  WallClimb = "Wall Climb",
  WaterWalking = "Water Walking",
  WMOCollision = "WMO Collision",
  WMORenderer = "WMO Renderer",
  Zoomhack = "Zoomhack"  
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
