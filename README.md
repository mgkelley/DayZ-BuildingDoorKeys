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

![](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/ScreenShots/Proccess.png?raw=true)

# Building.json
```"Version"```<br>
Integer<br>
Do not change, used for automatic conversion of old settings.
<br>
<br>
```"UpdateFrequecy"```<br>
Float<br>
Default is 10<br>
Update frequencey in seconds of the Building Key Manager.
<br>
<br>
```"LogBuildingTypesLoad"```<br>
```"LogAction"```<br>
```"LogActionConditions"```<br>
Bool<br>
Used to toggle output to log file.
<br>
<br>
```"EnableTerritoryFlag"```<br>
Bool
* 0 = Disable automatic creation of territory flag when key paired with building.
* 1 = Enable automatic creation of territory flag when key paired with building.


```"InitialFlagHeight"```<br>
Float<br>
Initial height of flag if territory flag pole enabled. Valid range is 0 thru 5. 0 is not recomended because DayZ central economy could _Immediatley_ run and trigger flag pole to be deleted and building unpaired from key.
<br>
<br>
```"DefaultFlagType"```<br>
String<br>
Default = "Flag_DayZ" .Class of flag to be attached to flag pole.
<br>
<br>
```"DefaultFlagTexture"```<br>
String<br>
Default = "dz\\gear\\camping\\Data\\Flag_DAYZ_co.paa". Texture to use for flag.
<br>
<br>
```"TerritoryFlagLifeAccel"```<br>
Float
* 0 = Flag will not lower.
* 1 = Flag will lower at default Central Economy rate.
* 40000 = Flag will lower in 2 minutes.


```"MaxDoorHealth"```<br>
Float
* 0 = Door damage disabled. Locks cant to broken.
* 100000  Default, door lock will open after 330 5.56 rounds.


```"DoorTypes"```<br>
Array<br>
List all valid building configurations and setting for their keys.
```
        {
            "KeyClass": "DoorKeyType1",
            "KeyName": "House Key",
            "BuildingClass": "Land_House_1W01",
            "BuildingName": "One Bedroom House",
            "BuildingDescription": "Red and green one bedroom house",
            "FlagOffset": [-0.8857420086860657, -2.796905994415283, 3.497070074081421],
            "FlagOreintation": [180, 0, 0]
        },
```
<br>
<br>

# Valid flag classes
Flag_Chernarus<br>
Flag_Chedaki<br>
Flag_NAPA<br>
Flag_CDF<br>
Flag_Livonia<br>
Flag_Altis<br>
Flag_SSahrani<br>
Flag_NSahrani<br>
Flag_DayZ<br>
Flag_LivoniaArmy<br>
Flag_White<br>
Flag_Bohemia<br>
Flag_APA<br>
Flag_UEC<br>
Flag_Pirates<br>
Flag_Cannibals<br>
Flag_Bear<br>
Flag_Wolf<br>
Flag_BabyDeer<br>
Flag_Rooster<br>
Flag_LivoniaPolice<br>
Flag_CMC<br>
Flag_TEC<br>
Flag_CHEL<br>
Flag_Zenit<br>
Flag_HunterZ<br>
Flag_BrainZ<br>
Flag_Rex<br>
Flag_Zagorky<br>
Flag_Crook<br><br>

: "Flag_DayZ",
    "DefaultFlagTexture": "dz\\gear\\camping\\Data\\Flag_DAYZ_co.paa",
    "TerritoryFlagLifeAccel": 1,
    "MaxDoorHealth": 100000,
    "DoorTypes": [
        {
            "KeyClass": "DoorKeyType1",
            "KeyName": "House Key",
            "BuildingClass": "Land_House_1W01",
            "BuildingName": "One Bedroom House",
            "BuildingDescription": "Red and green one bedroom house",
            "FlagOffset": [-0.8857420086860657, -2.796905994415283, 3.497070074081421],
            "FlagOreintation": [180, 0, 0]
        },

        

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

# Valid flag classes
class Flag_Chernarus extends Flag_Base {};
class Flag_Chedaki extends Flag_Base {};
class Flag_NAPA extends Flag_Base {};
class Flag_CDF extends Flag_Base {};
class Flag_Livonia extends Flag_Base {};
class Flag_Altis extends Flag_Base {};
class Flag_SSahrani extends Flag_Base {};
class Flag_NSahrani extends Flag_Base {};
class Flag_DayZ extends Flag_Base {};
class Flag_LivoniaArmy extends Flag_Base {};
class Flag_White extends Flag_Base {};
class Flag_Bohemia extends Flag_Base {};
class Flag_APA extends Flag_Base {};
class Flag_UEC extends Flag_Base {};
class Flag_Pirates extends Flag_Base {};
class Flag_Cannibals extends Flag_Base {};
class Flag_Bear extends Flag_Base {};
class Flag_Wolf extends Flag_Base {};
class Flag_BabyDeer extends Flag_Base {};
class Flag_Rooster extends Flag_Base {};
class Flag_LivoniaPolice extends Flag_Base {};
class Flag_CMC extends Flag_Base {};
class Flag_TEC extends Flag_Base {};
class Flag_CHEL extends Flag_Base {};
class Flag_Zenit extends Flag_Base {};
class Flag_HunterZ extends Flag_Base {};
class Flag_BrainZ extends Flag_Base {};
class Flag_Rex extends Flag_Base {};
class Flag_Zagorky extends Flag_Base {};
class Flag_Crook extends Flag_Base {};
