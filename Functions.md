# Functions
* [SendPacketRaw](#sendpacketraw)
* [SendPacket](#sendpacket)
* [ProcessTankUpdatePacket](#processtankupdatepacket)
* [OnVariantList](#onvariantlist)
* [OnTextGameMessage](#ontextgamemessage)
* [HandleTrackPacket](#handletrackpacket)
* [GetPlayer](#getplayer)
* [GetPlayers](#getplayers)
* [GetObjects](#getobjects)
* [GetTile](#gettile)
* [GetTiles](#gettiles)
* [GetInventory](#getinventory)
* [GetLocal](#getlocal)
* [DrawScaled](#drawscaled)
* [UpdateCamera](#updatecamera)
* [WorldToScreen](#worldtoscreen)
* [ScreenToWorld](#screentoworld)
* [IsKeyPressed](#iskeypressed)
* [Log](#log)
* [FindPath](#findpath)
* [SetFPSLimit](#setfpslimit)

## SendPacketRaw
```lua
SendPacketRaw(GamePacket packet)
```

Sends [GamePacket](Structs.md#gamepacket) to server

Example:
```lua
-- Sends wear clothing packet to server
packet = {}
packet.type = 10 -- PACKET_ITEM_ACTIVATE_REQUEST
packet.int_data = 48 -- Clothing ID (Jeans)
SendPacketRaw(packet)
```


## SendPacket
```lua
SendPacket(int type, string packet)
```

Sends text packet with selected type to server

Example:
```lua
-- Sends respawn packet to server
SendPacket(2, "action|respawn")
```

## ProcessTankUpdatePacket
```lua
ProcessTankUpdatePacket(GamePacket packet)
```

Sends [GamePacket](Structs.md#gamepacket) to client

Example:
```lua
-- idk
packet = {}

ProcessTankUpdatePacket(packet)
```

## OnVariantList
```lua
OnVariantList(Variantlist varlist)
```

Sends [Variantlist](Structs.md#variantlist) to client

Example:
```lua
-- Sends OnConsoleMessage to client
varlist = {}
varlist[0] = "OnConsoleMessage" -- Function name
varlist[1] = "Hello!" -- Param 1
OnVariantList(varlist)
```

## OnTextGameMessage
```lua
OnTextGameMessage(string text)
```

Sends GameMessage text to client

Example:
```lua
-- Sends action|log to client
text = [[action|log
msg|Hello
]]
OnTextGameMessage(text)
```

## HandleTrackPacket
```lua
HandleTrackPacket(string text)
```

Sends TrackPacket text to client

Example:
```lua
-- Sends empty track packet to client
text = ""
OnTextGameMessage(text)
```

## GetPlayer
```lua
GetPlayer(string name)
```

Returns selected players [NetAvatar](#Structs.md#netavatar) struct

Example:
```lua
-- Changes player pelle's name to "lol"
plr = GetPlayer("pelle")
plr.name = "lol"
```

## GetPlayers
```lua
GetPlayers()
```

Returns table of players [NetAvatar](#Structs.md#netavatar) structs in current world

Example:
```lua
-- Changes all names to "lol"
for _, player in pairs(GetPlayers()) do
player.name = "lol"
end
```

## GetObjects
```lua
GetObjects()
```

Returns table of all [WorldObjects](Structs.md#worldobject) in current world

Example:
```lua
-- Sets every objects count to 200
for _, object in pairs(GetObjects()) do
object.count = 200
end
```

## GetTile
```lua
GetTile(int x, int y)
```

Returns world [Tile](Structs.md#tile) in selected position

Example:
```lua
-- Sets tile 0, 0 foreground id to 242
tile = GetTile(0, 0)
tile.fg = 242
```

## GetTiles
```lua
GetTiles()
```

Returns table of all [Tiles](Structs.md#tile) in current world

Example:
```lua
-- Sets all tiles foreground ids to 0
for _, tile in pairs(GetTiles()) do
tile.fg = 0
end
```

## GetInventory
```lua
GetInventory()
```

Returns table of all [InventoryItems](Structs.md#inventoryitem)

Example:
```lua
-- Logs all item ids in your inventory
for _, item in pairs(GetInventory()) do
Log(item.id)
end
```

## GetLocal
```lua
GetLocal()
```

Returns local players [NetAvatar](Structs.md#netavatar) struct

Example:
```lua
-- Sets local player name to "lol"
me = GetLocal()
me.name = "lol"
```

## DrawScaled

Soon

## UpdateCamera

Soon

## WorldToScreen
```lua
WorldToScreen(vec2 pos)
```

Returns screen coordinates of selected position

Example:
```lua
-- Logs local player x screen position
w2s = WorldToScreen(GetLocal().pos)
log(w2s.x)
```

## ScreenToWorld
```lua
ScreenToWorld(vec2 pos)
```

Returns world coordinates of selected position

Example:
```lua
-- Logs 0, 0 screen positions world x position
s2w = ScreenToWorld({0, 0})
Log(s2w.x)
```


## IsKeyPressed
```lua
IsKeyPressed(int key)
```

Returns true/false depending on if you are pressing selected key

Example:
```lua
-- Logs "A Pressed" if you press A key
while true do
if IsKeyPressed(VK_A) then
Log("A Pressed")
end
end
```

## Log
```lua
Log(string msg)
```

Logs message to Growtopia's console

Example:
```lua
-- Logs "Hello!" to Growtopia's console
log("Hello!")
```

## FindPath
```lua
FindPath(int x, int y)
```

Finds path to selected x, y and returns true/false if path is found

Example:
```lua
-- Finds path to top left corner of the world
FindPath(0, 0)
```

## SetFPSLimit
```lua
SetFPSLimit(float fps)
```

Sets Growtopia's fps limit to selected fps

Example:
```lua
-- Sets Growtopia's fps limit to 200
SetFPSLimit(200)
```

