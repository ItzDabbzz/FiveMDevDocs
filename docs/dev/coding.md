# FiveM Docs
- Home | https://docs.fivem.net/docs/
- Natives | https://docs.fivem.net/natives/
- Controls | https://docs.fivem.net/docs/game-references/controls/
- Console Commands | https://docs.fivem.net/docs/client-manual/console-commands/
- Server Commands | https://docs.fivem.net/docs/server-manual/server-commands/
- State Bags | https://docs.fivem.net/docs/scripting-manual/networking/state-bags/
- NUI Debugging | http://localhost:13172/
- DUI Information | https://docs.fivem.net/docs/scripting-manual/nui-development/dui/

# Wikis/Libs/Useful Sites/Tools
- QBCore Docs | https://bombayv.github.io/qbcore.github.io/#/
- Material Icons | https://fonts.google.com/icons?selected=Material+Icons
- Font Awesome Icons | https://fontawesome.com/v5.15/icons?d=gallery&p=2
- Pleb Masters Forge | https://forge.plebmasters.de/objects
- DurtyFree Master GTA Dumps | https://github.com/DurtyFree/gta-v-data-dumps
- FiveM React BoilerPlate | https://github.com/project-error/fivem-react-boilerplate-lua
- Online PolyZone Creator | https://skyrossm.github.io/PolyZoneCreator/?
- Gta5 Mod Maps | https://dielikekane.com/tag/gta-v-mod-map-street-names/

# Learning Resources
- Learn Lua in Y Minutes | https://learnxinyminutes.com/docs/lua/
- State Bag Usage | https://forum.cfx.re/t/how-to-use-state-bags/2093206
- Streaming Clothes and Props | https://forum.cfx.re/t/how-to-stream-clothes-and-props-as-addons-for-mp-freemode-models/3345474
- Adaptive Cards | https://github.com/NoahtheDeveloper/FiveM-Adaptive-Cards/blob/main/server.lua

# Info Dumps
- Animations List | https://alexguirre.github.io/animations-list/
- Animations Vid | https://www.youtube.com/watch?v=RZ45axHLmg8
- Animations Vid 2 | https://www.youtube.com/watch?v=51qfsG4zmUw

# Important Programs To Have
- Visual Studio Code | Programming IDE | https://code.visualstudio.com/
- MariaDB | [https://www.apachefriends.org/](https://mariadb.org/download/)
- HeidiSQL | Database IDE (or VSC extension: cweijan.vscode-mysql-client2) | https://www.heidisql.com/
- Filezilla FTP Client | To connect to the file system of a remote machine | https://filezilla-project.org/
- FiveM Server Artifacts | https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/
- OpenIV | https://openiv.com/
- Codewalker | https://discord.com/invite/BxfKHkk

# Visual Studio Code Addons
- Lua Language Server | https://marketplace.visualstudio.com/items?itemName=sumneko.lua
- OverExtended's CfxLua LLS Addon | https://marketplace.visualstudio.com/items?itemName=overextended.cfxlua-vscode
- Markdown All In One | https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one
- TODO Highlight | https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight
- Catppucin Theme | https://marketplace.visualstudio.com/items?itemName=Catppuccin.catppuccin-vsc
- Catppucin Icons | https://marketplace.visualstudio.com/items?itemName=thang-nm.catppuccin-perfect-icons

# Basics To Learn In Lua
- Get an understanding of the Syntax | https://learnxinyminutes.com/docs/lua/
- Printing to console
- Basic conditional statements (if/then/elseif/end)
- Variables - local vs global
- Loops - Types and which to use when
- Functions - Why they're important, when to use them, how to use parameters
- Arrays/Table Objects - What the difference is when to use each
- How to loop over arrays/tables

# Basics To Learn For FiveM
- Lua Programming Language | https://learnxinyminutes.com/docs/lua/
- Searching the FiveM docs for natives, controls, blips, markers, console/server commands | https://docs.fivem.net/docs/
- How to setup a vanilla and qb-core server with a database | https://docs.fivem.net/docs/server-manual/setting-up-a-server/
- Introduction to Resources/fxManifest | https://docs.fivem.net/docs/scripting-manual/introduction/introduction-to-resources/
- Create your first script | https://docs.fivem.net/docs/scripting-manual/introduction/creating-your-first-script/
- How the client/server system works with events | https://docs.fivem.net/docs/scripting-manual/working-with-events/ 
- Interacting with your (N)UI | https://docs.fivem.net/docs/scripting-manual/nui-development/
- CreateThreads and Waits

# Basics To Learn In QBCore
- Navigating the Docs | https://bombayv.github.io/qbcore.github.io/#/README
- Creating QBCore object variable client/server side
- Creating QBCore commands server side
- Getting PlayerData client and server side (has everything about a players character including job, gang, character info, money, name, licenses, metadata)
- Creating a new item and make it usable/do something server side
- Learn how to add/remove/detect money for a player server side
- Learn how to add/remove/detect items for a player client and server side
- Learn PolyZones and qb-target | 3rd eye interacting
- Learn qb-menu | Dynamic menu creation
- Learn qb-input | Dynamic input creation
- Learn progressbar | Dynamic progress bar creation
- QB-Core Important Events - OnPlayerLoaded/OnPlayerUnloaded/SetPlayerData - And how to use them to save PlayerData state locally instead of grabbing a new one every time you need it


# FiveM/Lua Practices/Optimizations
- Organize your resources into sub-folders | [vehicles] -> [cars], [boats], [planes] | etc.
- Ensure on entire folders when possible ( ensure [qb-core] )
- Dont use `Citizen.CreateThread()`, use `CreateThread()`
- Dont use `Citizen.Wait()`, use `Wait()`
- Use RegisterNetEvent("", function() end) for net events
- Use AddEventHandler("", function() end) for non-net events
- In server events, first set source equal to a constant (local src = source)
- Set unused variables to _ ( for _,v in ipairs(table) )
- Use PlayerPedId() instead of GetPlayerPed(-1)
- Use lua math vector for distance checking #( vector3() - vector3() ) instead of GetDistanceBetweenCoords
- Dynamically control thread wait times with variable
- All while loops should run on a variable, not "while true do"
- Never trust data from client on the server side. Double check everything. Injectors can send custom parameters to any server function!
- All item/cash adds/removes should be done server side behind verification
- Instead of table.insert(tableName, value) use tableName[#tableName+1] = value
- Instead of ( if something ~= nil then ) use ( if something then ) - Catches all values but nil/false (can use NOT keyword before that too!)
- Localize as many functions and variables as possible. Lua can read them faster.
- Utilize the onPlayerLoaded, onJobUpdate, onGangUpdate, onPlayerUnloaded, setPlayerData and other event handlers to handle PlayerData state locally. It will only update when changed! Do this instead of asking QBCore for a fresh version every time you need it. 
- Use next(TABLEHERE) in your conditionals to see if a table is empty or not ( if next(data) then print('I have data!') end )
- con_miniconChannels script:* in f8 console will show console prints and errors on your screen


# Array vs Object looping
```lua
-- Looping through an object table
Config.Table = {
    ['a'] = 1,
    ['b'] = 2,
    ['c'] = 3,
}

-- prints a,1 | b,2 | c,2
for key, value in pairs(Config.Table) do
    print(key, value)
end

--- Looping through an array table
Config.Array = { "d", "e", "f" }

-- prints 1,d | 2,e | 3,f
for index, value in ipairs(Config.Array) do
    print(index, value)
end
```


# Properly Managing PlayerData State Locally

?> You can use these events to manage local PlayerData state properly. Instead of asking QBCore what your player data is every time something gets called, we just save it locally, and only change it when it gets changed! You can use this for items tracking as well if you only want to track items instead of the whole playerdata object.

```lua
local QBCore = exports['qb-core']:GetCoreObject()

-- Handles state on resource start (useful for live resource restarts). Will set to empty brackets {} if character not found yet.
local PlayerData = QBCore.Functions.GetPlayerData()

-- Handles state right when the player selects their character and location.
RegisterNetEvent('QBCore:Client:OnPlayerLoaded', function()
    PlayerData = QBCore.Functions.GetPlayerData()
end)

-- Resets state on logout, in case of character change.
RegisterNetEvent('QBCore:Client:OnPlayerUnload', function()
  PlayerData = {}
end)

-- Handles state when PlayerData is changed at all.
RegisterNetEvent('QBCore:Player:SetPlayerData', function(_PlayerData)
    PlayerData = _PlayerData
end)```


# Talking between the client and the UI.

Client -> UI
client.lua
```lua
SendNUIMessage({
    action = "DoSomething",
    data = data
})
```

script.js
```js
window.addEventListener("message", (event) => {
    const data = event.data;
    const action = data.action;

    switch (action) {
        case "DoSomething":
            // Do something
        case "DoNothing":
            // Do nothing
        default:
            return;
    }
});
```

UI -> Client
script.js
```js
$.post(`https://${GetParentResourceName()}/IDidAThing`,
        JSON.stringify({ data: 'Hi Dad', test: 'This is a test' })
    );

```

client.lua
```lua
RegisterNUICallback("IDidAThing", function(data, cb)
    print(data.data) -- Hi Dad
    print(data.test) -- This is a test
    cb("ok")
end)

````


# OxMySQL

?> Helpful documentation. https://overextended.github.io/oxmysql/usage/

```js
// Returns all columns for one row
MySQL.fetchSingle 

// Returns number of affected rows
MySQL.execute

// Return the insert id if valid
MySQL.insert 

// Generic function for any type of query, returns all data, inserted ids, affected rows, etc based on query
MySQL.query 
MySQL.fetchAll 
MySQL.prepare

// Attempts to execute multiple queries, and if all are valid, processes them and returns true
MySQL.transaction 

// Return first column for a single row
MySQL.fetchScalar
```
All of these can be MySQL.async or MySQL.sync. 

Async will have a callback parameter that returns your result.
Sync will hold code execution till done, and return your result from the request, so set a variable equal to the function to get it.

```lua
-- Sync
local result = MySQL.Async.fetchOne('SELECT tattoos FROM player_tattoos WHERE citizenid = ?', { Player.PlayerData.citizenid })

-- Async
MySQL.Async.fetchOne('SELECT tattoos FROM player_tattoos WHERE citizenid = ?', { Player.PlayerData.citizenid }, function(result)
    -- Stuff here
end)
````
