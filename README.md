# esx_ambulancejob

ESX Ambulance Job is an plugin for ESX with features:

- Adds death screen, with early respawn timer and bleed out timer
- Vehicle garages, revive menu and more for on duty EMS

## Requirements

* Auto mode
   - [esx_skin](https://github.com/ESX-Org/esx_skin)
   - [esx_vehicleshop](https://github.com/ESX-Org/esx_vehicleshop)

* Player management (boss actions)
   - [esx_society](https://github.com/ESX-Org/esx_society)

## Download & Installation

### Using [fvm](https://github.com/qlaffont/fvm-installer)
```
fvm install --save --folder=esx esx-org/esx_ambulancejob
```

### Using Git
```
cd resources
git clone https://github.com/ESX-Org/esx_ambulancejob [esx]/esx_ambulancejob
```

### Manually
- Download https://github.com/ESX-Org/esx_ambulancejob/archive/master.zip
- Put it in the `[esx]` directory

## Installation
- Import `esx_ambulancejob.sql` in your database
- If you want player management you have to set `Config.EnablePlayerManagement` to `true` in `config.lua`
- Add this in your `server.cfg`:

```
start esx_ambulancejob
```
