# Borderlands Twitch Integration
A Streamlabs Chatbot Script that applies modifiers to Borderlands 2 and TPS live as Twitch chat votes on them.

![Chatbot Script and OBS Overlay](https://i.imgur.com/a1TvvTQ.jpg)

Borderlands Twitch Integration runs entirely within Streamlabs Chatbot, including its operation, settings, and updating of the stream overlay. Modifiers are applied to the game **fully automatically** once voted on.

Voting begins when the script is turned on in Chatbot. A list of candidates is chosen randomly from the modifiers enabled in settings, and users may vote for them for the duration of the voting cycle specified. At the end of the cycle, the winning modifier is applied, a new list of candidates is presented, and the process repeats. The current modifiers available in settings are as follows:

| | | | | |
| --- | --- | --- | --- | --- |
| Gravity | Grenade Only | Jumping Only | Vampire | Weapon Knockback |
| Game Speed | Rockets Only | No HUD | More Badasses | Instant Respawns |
| Movement Speed | Melee Only | Third Person | Enemy Movement Speed | No Ammo Pickups |
| Entity Size | Crits Only | Inverted Aiming | Enemy Damage | Slippery Guns |
| Field Of View | No Crits | No Forward Movement | Candy Drops | Heavy Falls |
| Damage | Upside Down World | No Shields | No Friction | |

A live overlay is provided for use in streaming software such as OBS. This provides information on the current modifier, voting instructions, the list of candidates, and a countdown timer for the current voting cycle.

Borderlands Twitch Integration is made possible thanks to [c0dycode's CommandInjector](https://github.com/c0dycode/BL-CommandInjector), via the [BLIO set of methods](https://github.com/mopioid/BLIO). Special thanks to FromDarkHell for assistance with certain modifiers such as [No HUD](https://github.com/BLCM/BLCMods/blob/master/Borderlands%202%20mods/FromDarkHell/Misc/HUDHider.txt) and [Entity Size](https://github.com/BLCM/BLCMods/blob/master/Borderlands%202%20mods/FromDarkHell/Misc/BigLands.txt).

