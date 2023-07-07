# DayZ-BuildingDoorKeys
![](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/common/BuildingDoorKeys.png?raw=true)

Keys that can be paired to buildings, enabling all doors to be locked and unlocked.
Each key is assigned a specific building type when spawned.
* Includes Admin keys that can be spawned with an admin tool, enabling any door to be unlocked and any building to be unpaired from a key.
* DayZ vanilla Lockpicks do NOT work on a door locked by these keys or any door of a building that has been paired to a key.
* Door damage can be disabled or increased to prevent raiding or increase amount of damage required to break a door lock.
* DayZ vanilla _Territory Flag Pole_ can be enabled to create a refresh area at a paired building. When the flag lifetime expires from being lowered by the Central Economy System in Dayz, the building will be unpaired from its key, all doors unlocked and the flag pole deleted.
* Key types are completely configurable in _Building.json_ file stored in the 'ServerProfile' folder. Vanilla and modded buildings can be configured to support keys and the _Territory Flag Pole_ position and rotation relative the the building can be set.
* Each configured key can be set to reference a predefined _spawnable_type_. Each _spawnable_type_ can have unique usage, tier and nominal settings.
* Paired buildings are stored in _"ServerProfile//BuildingDoorKeys//Persistence//"_ so individual or all paired buildings can be wiped seperate from DayZ storage.
<br>
<br>

![](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/common/Proccess.png?raw=true)
<br>
<br>
# Building.json
```Version```
<br> 
Integer<br>
Do not change, used for automatic conversion of old settings.
<br>
<br>
```UpdateFrequecy```<br>
Float<br>
Default is 10<br>
Update frequencey in seconds of the Building Key Manager.
<br>
<br>
```LogBuildingTypesLoad```<br>
```LogAction```<br>
```LogActionConditions```<br>
Bool<br>
Used to toggle output to log file.
<br>
<br>
```EnableTerritoryFlag```<br>
Bool
* 0 = Disable automatic creation of territory flag when key paired with building.
* 1 = Enable automatic creation of territory flag when key paired with building.

<br>```InitialFlagHeight```<br>
Float<br>
Initial height of flag if territory flag pole enabled. Valid range is 0 thru 5. 0 is not recomended because DayZ central economy could _Immediatley_ run and trigger flag pole to be deleted and building unpaired from key.
<br>
<br>
```DefaultFlagType```<br>
String<br>
Default = _"Flag_DayZ"_ .Class of flag to be attached to flag pole. [Valid classes](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/common/FlagClasses.md)
<br>
<br>
```DefaultFlagTexture```<br>
String<br>
Default = _"dz\\gear\\camping\\Data\\Flag_DAYZ_co.paa"_. Texture to use for flag.  [Valid Textures](https://github.com/mgkelley/DayZ-BuildingDoorKeys/blob/main/common/FlagTextures.md)
<br>
<br>
```TerritoryFlagLifeAccel```<br>
Float
* 0 = Flag will not lower.
* 1 = Flag will lower at default Central Economy rate.
* 40000 = Flag will lower in 2 minutes.

<br>```MaxDoorHealth```<br>
Float
* 0 = Door damage disabled. Locks cant to broken.
* 100000 = Default, door lock will open after 330 5.56 rounds.

<br>```KeyTypes```<br>
Array<br>
List all valid key settings with their paired building class names.
<br>
{
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```KeyClass```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;String<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Name of spawnable type to use for this key. Valid entries:<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;_"DoorKeyType1", "DoorKeyType2", "DoorKeyType3", "DoorKeyType4"_
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```KeyName```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;String<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Displayable name of the key.
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```BuildingClass```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;String<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Literal class name of the building this key can pair to.
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```BuildingName```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;String<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Displayable name of the building.
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```BuildingDescription```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;String<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Displayable description of the building.
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```FlagOffset```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Vector<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Relative offset from building pivot point to flag position.
<br>
<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;```FlagOreintation```<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Vector<br>
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Relative rotation of flag to building.
<br>
}
<br>
<br>
