# PyWeaponWheel mod for Doom

The PyWeaponWheel is an addon that aims to be as compatible as possible with any mod or IWAD. It grabs all weapon actors, selects the ones that fit a certain criteria, and organizes them into a lovely wheel. This process is detailed in the README located inside the pk3. Despite its efforts, however, sometimes undesirable weapons creep onto the wheel. That is where the PYWHEEL lump comes in.

The PYWHEEL lump contains a series of definitions for mods that don't play nicely with the wheel for any reason. The mod contains its own collection of premade definitions for mods. However, what if a mod is not covered by this existing list? Well, you can include a PYWHEEL definition inside your own pk3! The mod will parse through all available PYWHEEL lumps that it can find. The syntax and parsing are a bit too lenient and wonky at the moment, but the base support is there.

The PyWeaponWheel is great not only for normal play, but its also a great enhancement for gamepad play! No need to fumble with your buttons trying to find the right weapon for the job, as you can now just pluck it out of the wheel and blast away your opposition. The mod is in an early state, but I'm releasing it to gather feedback on how it performs with the base game, mods, and more.

![PyWeaponWheel mod for Doom](https://i.imgur.com/dK4vHlB.png)

Check the PyWeaponWheel discussion over here: https://forum.zdoom.org/viewtopic.php?t=61061

## What Changed in VR Version?
* Since level freezing also locks up head-tracking so it is replaced by new codes to freeze all monsters and projectiles instead
* Mouse control for the weapon wheel is replaced by joystick control (off-hand joystick)
* When weapon wheel is open the player movement is disabled
* Releasing weapon wheel button no longer closes the wheel. Instead need to press "attack" or "use" button to select highlighted weapon and close weapon wheel.

## Known Issues
* Anything other than monsters and proectiles will not freeze when the weapon wheel is open including decorative actors, ACS scripts and platforms/lifts.
	
## How Does This Interact With Mods?

The addon goes through a list of all actors, and picks the ones that are weapons. Then, according to the player's current class, it determines which ones are available to the player. Mulit-class mods that use Weapon.SlotNumber or something similar will not work properly out of the box. It compiles those weapons into a list that the wheel then uses.

Here is the process of how the addon decides what icon to use:
* It checks for the inventory icon.
* If there is no inventory icon, it checks through all frames of the spawn state.
* If there is no valid sprite from the spawn state (like TNT1) then it goes to the first frame of the ready state.
* If there is no valid sprite from the ready state, then it falls back to a default icon, with the name of the weapon printed over it.
	
## Mods Confirmed To Work
* Doom Delta
* MetaDoom
* Juvenile Power Fantasy
* Argent
* LegenDoom
* Doom: The Golden Souls 2
* Project Babel
* QC: Doom Edition
* Death Foretold
* High Noon Drifter
* Samsara
* Weasel Presents: Terrorists!
* Hunter's Moon

## Credits
* DrPyspy - ZScript code, wheel graphics, etc.
* m8f - Fixed wheel crash
* Jimmy- Diet Log font
* ZZYZX - Crowbar placeholder graphic
* Ermac - Modified the codes to work better in VR