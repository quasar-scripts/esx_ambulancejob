# esx_ambulancejob

ESX Ambulance Job is an plugin for ESX with features:

- This system comes completely modified for Quasar Inventory.
- Adds death screen, with early respawn timer and bleed out timer
- Vehicle garages, revive menu and more for on duty EMS

## Quasar Inventory Modifications

ADD (line 1)
esx_ambulancejob/server/main.lua
```
QS = nil
TriggerEvent('qs-core:getSharedObject', function(library) QS = library end)
```

REPLACE
esx_ambulancejob:removeItemsAfterRPDeath
```
ESX.RegisterServerCallback('esx_ambulancejob:removeItemsAfterRPDeath', function(source, cb)
	local xPlayer = QS.GetPlayerFromId(source)
	local xPlayerx = ESX.GetPlayerFromId(source)
	xPlayer.ClearInventory()
	MySQL.Sync.execute("UPDATE `users` SET `inventory` = '"..QS.EscapeSqli(json.encode({})).."' WHERE `identifier` = '"..xPlayerx.identifier.."'")
	cb()
end)
```

## Requirements

* Auto mode
   - [esx_skin](https://github.com/ESX-Org/esx_skin)
   - [esx_vehicleshop](https://github.com/ESX-Org/esx_vehicleshop)

* Player management (boss actions)
   - [esx_society](https://github.com/ESX-Org/esx_society)

## Installation
- Import `esx_ambulancejob.sql` in your database
- If you want player management you have to set `Config.EnablePlayerManagement` to `true` in `config.lua`
- Add this in your `server.cfg`:

```
start esx_ambulancejob
```
