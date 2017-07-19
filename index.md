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

### GetDistanceFallen 
```lua
-- Return value: The total distance fallen since the player last started to fall or 0 if not currently falling (number)
GetDistanceFallen(); -- Returns the distance fallen
```

----------------------------------------------------
## Object Manager
### HasObjectManagerUpdated
```lua
-- Return value: Boolean
HasObjectManagerUpdated(); -- Returns if the in game objects available to the API have changed. Note: this is VERY useful to keep FPS high as you can cache a table of objects in your script and only update when required. 
```
### GetObjectCount
```lua
-- Return value: Int
GetObjectCount(); -- Get the number of objects in the object manager.

-- Available Aliases:
ObjectCount();
```

### GetObjectWithIndex
```lua
-- Return value: The Object
-- Argument 1: Object Index (Int)
GetObjectWithIndex(index); -- Get an object in the object manager from using its index

-- Available Aliases:
GetObjectFromIndex();
ObjectWithIndex();
```

### GetObjectWithPointer
```lua
-- Return value: The Object
-- Argument 1: Object Pointer formatted at Hex String. 0x123ABC
GetObjectWithPointer(pointer); -- Get an object in the object manager from its pointer.

-- Available Aliases:
ObjectWithPointer();
```

### GetObjectWithToken
```lua
-- Return value: The Object
-- Argument 1: A object token. Player, Target, Mouseover, etc.
GetObjectWithToken(pointer); -- Get an object in the object manager from its pointer.

-- Available Aliases:
ObjectWithToken();
GetObjectFromToken();
```

### GetObjectWithGUID
```lua
-- Return value: The Object
-- Argument 1: Object GUID. Note: This only accepts the GUID from ObjectGUID! Do not use ObjectFormattedGUID for this function
GetObjectWithGUID(guid); -- Get an object in the object manager from its GUID.
```

### GetObjectsOfType
```lua
-- Return value: Table of Objects of the specified types
-- Argument 1: ObjectType
GetObjectsOfType(ObjectType); -- Returns a table of objects of the specified type
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
### ObjectID
```lua
-- Return value: String
-- Argument 1: The Object
ObjectID(object); --  Get the objects Entry ID
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
-- Return value: Boolean
-- Argument 1: The Object
ObjectExists(object); --  Returns true if the specified objects still exists in the Object Manager
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

-- Available Aliases:
ObjectType();
```

### ObjectTypeMask
```lua
-- Return value: Int 
-- Argument 1: The Object
ObjectTypeMask(object); --  Returns the typemask of the object
```

### ObjectInteract
```lua
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
-- Return value: Boolean 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float). Default value: 3 radians
ObjectIsFacing(objectA, objectB[, marginOfError]); --  Get whether an object is facing another.

-- Available Aliases:
UnitIsFacing()
```

### ObjectIsBehind
```lua
-- Return value: Boolean 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float). Default value: 0.2 radians
ObjectIsBehind(objectA, objectB[, marginOfError]); --  Get whether an object is behind another.
```

### ObjectIsInfront
```lua
-- Return value: Boolean 
-- Argument 1: Object A
-- Argument 2: Object B
-- Argument 3: OPTIONAL: The margin of error for facing(float). Default value: 0.2 radians
ObjectIsInfront(objectA, objectB[, marginOfError]); --  Get whether an object is infront of another.
```

### ObjectIsType
```lua
-- Return value: Boolean 
-- Argument 1: Object
-- Argument 2: ObjectType
ObjectIsType(object, objectType); --  Returns true if the object if the specified type
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
### UnitMovementFlags
```lua
-- Return value: Int 
-- Argument 1: The Unit
UnitMovementFlags(unit); --  Gets the units movement flags
```

### UnitBoundingRadius
```lua
-- Return value: Int 
-- Argument 1: The Unit
UnitBoundingRadius(unit); --  Gets the units bounding radius
```

### UnitCombatReach
```lua
-- Return value: Int 
-- Argument 1: The Unit
UnitCombatReach(unit); --  Gets the units combat reach
```

### UnitTarget
```lua
-- Return value: The target Object or nil if there is none
-- Argument 1: The Unit
UnitTarget(unit); --  Gets the Target Object
```

### UnitCreator
```lua
-- Return value: The creator Object or nil if there is none
-- Argument 1: The Unit
UnitCreator(unit); --  Gets the creator Object
```

### UnitCanBeLooted
```lua
-- Return value: Boolean
-- Argument 1: The Unit
UnitCanBeLooted(unit); --  Returns if the Unit can be looted

-- Available Aliases:
UnitIsLootable()
```

### UnitCanBeSkinned
```lua
-- Return value: Boolean
-- Argument 1: The Unit
UnitCanBeSkinned(unit); --  Returns if the Unit can be skinned

-- Available Aliases:
UnitIsSkinnable()
```

### UnitSetDisplayID
```lua
-- Return value: Boolean
-- Argument 1: The Unit
-- Argument 2: The display ID (Int)
UnitSetDisplayID(unit, id); --  Returns a boolean that specifies if the ID was set or not. UnitUpdateModule must be called for the change to be displayed.
```

### UnitUpdateModel
```lua
-- Argument 1: The Unit
UnitUpdateModel(unit); --  Refreshes the model drawn for the supplied Unit. Call this after UnitSetDisplayID()
```

----------------------------------------------------
## World 
### TraceLine
```lua
-- Return value: The X, Y, and Z coordinates of the hit position, or nil, nil, nil if nothing was hit 
-- Argument 1: The starting X coordinate (float)
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

### IsAoEPending
```lua
-- Return value: Boolean
IsAoEPending(); -- Returns if a AoE spell is pending
```

### ClickPosition
```lua
-- Argument 1: The starting X coordinate (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: OPTIONAL: Should right click instead of left. Default value:  false (Boolean)
ClickPosition(x, y, z[, Right]); -- Simulate a click at a position in the game-world.

-- Available Aliases:
CastAtPosition();
```

### CancelPendingSpell
```lua
CancelPendingSpell(); -- Cancels the pending AoE spell
```

### WorldToScreen
```lua
-- Return value: The X and Y screen coordinates for the XYZ coordinates
-- Argument 1: The X coordinate (float)
-- Argument 2: The Y coordinate (float)
-- Argument 3: The Z coordinate (float)
WorldToScreen(x, y, z); -- Get the screen coordinates relative from World coordinates
```

### IsInFront
```lua
-- Return value: Boolean
-- Argument 1: The X coordinate (float)
-- Argument 2: The Y coordinate (float)
-- Argument 3: The Z coordinate (float)
IsInFront(x, y, z); -- Return whether the given coordinates are in front of WoW's camera
```

----------------------------------------------------
## Hacks 
### IsHackEnabled
```lua
-- Return value: Boolean
-- Argument 1: The name of the hack you wish to check the enabled status for (String)
IsHackEnabled(name); -- Returns true if the specified hack is enabled.
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
-- Return value: Table of strings
-- Argument 1: Path of directory (String) Note: Directory path should be formatted like "C:\\GameHackingTools\\"
GetDirectoryFiles(path); -- Returns the file path to each file found in the specified directory.
```

### GetSubdirectories
```lua
-- Return value: Table of strings
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

### LoadScript
```lua
-- Return value: Any return values from the script
-- Argument 1: the name of the script to load (including the file extension) (String)
LoadScript(script); -- Runs an entire lua script

-- Available Aliases:
/load <filename> -- Usable only from the game chat window
```
### GetScriptName 
```lua
-- Return value: The script file name (string)
GetScriptName (); -- Get the file name of the currently executing script
```

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
-- Return value: Boolean
IsForeground(); -- Returns true if the game client is the foremost window.
```

### GetSpellName 
```lua
-- Return value: Spell Name (string)
-- Argument 1: spellID (number)
GetSpellName(spellID); -- Returns the spell name
```

### GetAspectRatio
```lua
-- Return value: The aspect ratio (number)
GetAspectRatio(); -- Returns the aspect ratio
```

----------------------------------------------------
## Callbacks

### AddFrameCallback 
```lua
-- Argument 1: Callback (function)
AddFrameCallback(callback); -- Adds the specified callback and calls it every frame
```

### AddTimerCallback  
```lua
-- Argument 1: The number of seconds to wait between calls (number)
-- Argument 2: Callback (function)
AddTimerCallback(seconds, callback); -- Adds the specfied callback and after the specified duration
```

### AddEventCallback   
```lua
-- Argument 1: The wow event (http://wowprogramming.com/docs/events) (string)
-- Argument 2: Callback (function)
AddEventCallback (eventname, callback); -- Adds the specfied callback that will be called every time the specified event is called. It should be noted that the callback will be called with the event arguments.
```

----------------------------------------------------
## Math

### GetDistanceBetweenPositions
```lua
-- Return value: float
-- Argument 1: The starting X coordinate (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: The ending X coordinate (float)
-- Argument 5: The ending Y coordinate (float)
-- Argument 6: The ending Z coordinate (float)
GetDistanceBetweenPositions(X, Y, Z, X2, Y2, Z2); -- Returns the distance between the two positions
```

### GetAnglesBetweenPositions
```lua
-- Return value: float
-- Argument 1: The starting X coordinate (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: The ending X coordinate (float)
-- Argument 5: The ending Y coordinate (float)
-- Argument 6: The ending Z coordinate (float)
GetAnglesBetweenPositions(X, Y, Z, X2, Y2, Z2); -- Returns the distance angle between the two positions
```

### GetPositionFromPosition
```lua
-- Return value: X, Y, Z (floats)
-- Argument 1: The starting X coordinate (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: The distance required (float)
-- Argument 5: The angle from the position (float)
-- Argument 6: The pitch from the position (float)
GetPositionFromPosition(X, Y, Z, dist, angle, pitch); -- Returns the X,Y,Z positions that are the specified distance away from starting coordinates
```

### GetPositionBetweenPositions
```lua
-- Return value: X, Y, Z (floats)
-- Argument 1: The starting X coordinate (float)
-- Argument 2: The starting Y coordinate (float)
-- Argument 3: The starting Z coordinate (float)
-- Argument 4: The ending X coordinate (float)
-- Argument 5: The ending Y coordinate (float)
-- Argument 6: The ending Z coordinate (float)
-- Argument 7: The distance from starting coordinates (float)
GetPositionBetweenPositions(X, Y, Z, X2, Y2, Z2, dist); -- Returns the X,Y,Z positions that are the specified distance away from starting coordinates while staying in line with the ending coordinates
```

----------------------------------------------------
## Enums
Note: You can dump all the latest version of these enums ingame when wToolkit is running with the command .dumpluafiles

### Hacks
Depending on the licence for the currently authenticated user you will get one of the following lists for hacks:

#### Lite
```lua
Hacks = {
  AntiAFK = "Anti-AFK",
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
  AntiAFK = "Anti-AFK",
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
  TrackNonCombatPets = "Track Non-Combat Pets",
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

### ObjectTypes

```lua
ObjectTypes = { 
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
