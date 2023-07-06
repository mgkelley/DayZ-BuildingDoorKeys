# DayZ-BuildingDoorKeys
![](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/ScreenShots/BuildingDoorKeys.png?raw=true)

Keys that can be paired to buildings, enabling all doors to be locked and unlocked.
Each key is assigned a specific building type when spawned.
* Includes Admin keys that can be spawned with an admin tool, enabling any door to be unlocked and any building to be unpaired from a key.
* DayZ vanilla Lockpicks do NOT work on a door locked by these keys or any door of a building that has been paired to a key.
* Door damage can be disabled or increased to prevent raiding or increase amount of damage required to break a door lock.
* DayZ vanilla _Territory Flag Pole_ can be enabled to create a refresh area at a paired building. When the flag lifetime expires from being lowered by the Central Economy System in Dayz, the building will be unpaired from its key, all doors unlocked and the flag pole deleted.
* Key types are completely configurable in a .json file stored in the 'ServerProfile' folder. Vanilla and modded buildings can be configured to support keys and the _Territory Flag Pole_ position and rotation relative the the building can be set.
* Each configured key can be set to reference a predefined _spawnable_type_. Each _spawnable_type_ can have unique usage, tier and nominal settings.

```diff
+ -! Warning !-
```
https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/ScreenShots/ff0000?text=hello
- ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `#f03c15`

  

There are _Weapons, Weapons Attachments, Clothing, Clothing Accessories, Consumables, Medical, Vehicles, Vehicle Parts, Components_ and _Building Supplies traders_.

ATM Objects are Blue Lockers.
<br />Most areas have survivor lounge area with fire pit and all areas have water well.

# Instructions
Place files for the traders you want from _'traders'_ folder into 'mpmissions/expansion.enoch/expansion/traders/' on your server,<br />
Place files for the trader areas you want from _'objects'_ folder into 'mpmissions/expansion.enoch/expansion/objects/' on your server.

Also supplied are .json files for SafeZone, Map Markers and Land Spawn Positions.<br />

_'SafeZoneSettings.json_ (Contains Safe Zones for traders)'<br />
Merge with 'mpmissions/expansion.enoch/expansion/settings/SafeZoneSettings.json' on your server.<br />

_'MapSetting.json'_ (Contains Map Markers for traders) <br />
Merge with 'mpmissions/expansion.enoch/expansion/settings/MapSettings.json' on your server.<br />

_'MarketSetting.json'_ (Contains Land Spawn Positions for vehicel traders)<br/>
Merge with 'mpmissions/expansion.enoch/expansion/settings/MarketSettings.json' on your server.<br />
<br />
NOTE: These .map Objects rely on '@BuilderItems' mod that is embeded in DayZ-Expansion. If you try to use them seperate from Expansion
be sure to include the '@BuilderItems' mod.<br />
Some objects are supplied by DayZ-Expansion, the ATM lockers, and will not spawn seperate from DayZ-Expansion.<br />
<br />

