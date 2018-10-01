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

## Installation

Your game must be hexedited for mods to be able to make changes in game. If you have not done this previously, [Borderlands Community Mod Manager](https://github.com/BLCM/BLCMods/wiki/Borderlands-Community-Mod-Manager) will do it for you.

For Borderlands Twitch Integration to be able to interact with the game, you must add a few things to the game's Win32 folder. If you already have CommandInjector installed, you may skip ahead to [installing Borderlands Twitch Integration](#installing-borderlands-twitch-integration).

### Installing CommandInjector

1. Quit the game if it is running.
2. [Download the latest version of `ddraw.dll` (A.K.A. PluginLoader).](https://github.com/c0dycode/BorderlandsPluginLoader/releases)
3. Locate the `Win32` folder within your game's `Binaries` folder. ![Win32 folder](https://i.imgur.com/t6OI06l.png)

4. Copy `ddraw.dll` to the `Win32` folder. ![ddrawl.dll](https://i.imgur.com/FHfiSqg.png)

5. In the `Win32` folder, create a folder called `Plugins`. ![Plugins folder](https://i.imgur.com/CDdoKDs.png)

7. [Download the latest version of CommandInjector.](https://github.com/c0dycode/BL-CommandInjector/blob/master/CommandInjector.zip)

6. Open the `CommandInjector.zip` file to view its contents. ![CommandInjector.zip](https://i.imgur.com/r1I3b26.png)

7. Copy `CommandInjector.dll` (BL2) or `CommandInjectorTPS.dll` (TPS) to the `Plugins` folder you created. ![CommandInjector.dll](https://i.imgur.com/U9OSqcV.png)

### Installing Borderlands Twitch Integration

If you have never used the "Scripts" feature of Streamlabs Chatbot, you must perform setup for scripts to function. [See here for a guide on how to do so.](https://www.youtube.com/watch?v=l3FBpY-0880)

1. [Download the latest version of Borderlands Twitch Integration.](https://github.com/mopioid/Borderlands-Twitch-Integration/releases)

2. Navigate to the Scripts section in Streamlabs Chatbot's sidebar, and click the "Import" button in the top right. ![Import Script](https://i.imgur.com/joi7aYY.png)

3. Select the `BorderlandsTwitchIntegration.zip` file you downloaded. ![Open BorderlandsTwitchIntegration.zip](https://i.imgur.com/5qbecBl.png)

4. Chatbot should provide a dialog confirming that the script has been installed, and Borderlands Integration should appear in your list of scripts. ![Installed Borderlands Twitch Integration](https://i.imgur.com/Kc0w7La.png)

5. If you would like to configure the overlay in your streaming software, [follow the instructions here on doing so](https://github.com/StreamlabsSupport/Streamlabs-Chatbot/wiki/Script-overlays).
