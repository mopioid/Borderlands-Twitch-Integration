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

## Usage

Borderlands Twitch Integration begins when the "Enabled" checkbox is checked next to it in the list of Chatbot Scripts. During this initial voting cycle, a random modifier is applied (chosen from the list of all enabled modifiers).

At the start of each voting cycle, the voting cycle clock begins counting down. The bot announces the winning modifier in chat, followed by the new list of candidates to vote on, as well as voting instructions. Users may begin voting immediately. The stream overlay is continuously updated with the currently active modifier, the current modifier candidates, and the live voting timer.

Users may change their votes during a voting cycle, simply by revoting. (Their vote is not counted twice, but changed to the candidate they voted to last.)

In the event of a tie at the end of a voting cycle, a random modifier is select from the list of forerunners.

Borderlands Twitch Integration is turned off by unchecking the same "Enabled" box used to turn it on.

While Borderlands Twitch Integration is running, four buttons are provided in script's UI in Chatbot:

* __Pause Modifier__: Temporarily disable the currently active modifier, and pause the voting timer. Users may still vote on the next modifier while the current one is paused.
* __Unpause Modifier__: Reapply the current modifier if it has been paused, and resume counting down the voting timer.
* __Skip Modifier__: End the current voting cycle early, select a new winning modifier, and begin the next voting cycle. 
* __Reapply Modifier__: In the event of a malfunction (e.g. needing to relaunch the game), resend the current modifier to the game to ensure it is fully applied.

## Configuration

Borderlands Twitch Integration provides a number of options to control its functionality. All of them may be changed at any time; they take effect when the "Save Settings" button is clicked, even if the script is already active.

### General Settings

* __Modifier Duration__: The duration (in seconds) of each modifier and voting cycle. Setting this to 180, for example, will enable each modifier for three minutes while users vote on the next one. Changes to this will take effect immedately (mid-cycle).
* __Number Of Candidates__: How many modifiers should be offered to users to choose from each voting cycle. Changes to this will take effect at the end of each voting cycle. This should not exceed the number of modifiers enabled under the "Modifiers" settings.
* __Voting Instructions__: The instructions provided to users in chat and in the stream overlay.
* __Testing Mode__: Disable voting related messages in chat. Instead, messages can be viewed in Chatbot's script logs (found in the top right of the Scripts pane).

### Voting Permissions

Borderlands Twitch Integration can limit voting to users matching specific criteria:

* __Everyone__: Allow everyone to vote. This should be disabled if you would like to limit voting to the user critera below.
* __Moderators__: Allow Twitch moderators and users designated as "Editors" in Streamlabs Chatbot to vote.
* __Subscribers__: Allow Twitch and GameWisp subscribers to vote.
* __Regulars__: Allow users designated as "Regulars" in Streamlabs Chatbot to vote.
* __Minimum Rank__: If this is not blank, allow users with the specified minimum rank in Streamlabs Chatbot to vote.
* __Specific Users__: A list of additional users, separated by commas, who are specifically allowed to vote.

When attempting to vote, if a user does not meet any of the above critera, their vote will not be counted, and the bot will reply to them with a list of critera they may hit to qualify ("Moderators" and "Specific Users" are not displayed).

Additional options are available to limit voting:

* __Currency Cost__: If greater than 0, the amount of currency users pay for each vote. They must still meet the criteria required to vote as specified above. If they cannot afford to vote, the bot replies to them with the amount required, as well as their current balance.
* __Allow !vote In Chat__: Allow users to use the !vote command in chat. Disable this if you would like to limit voting to whispers.
* __Allow !vote In Whisper__: Allow users to whisper the bot to vote.

### Modifiers

At any time, individual modifiers may be enabled or disabled. Disabled modifiers will not appear as candidates for voting. Changes take effect the next voting cycle.

### Stream Overlay

Configuration of the stream overlay is done by applying custom CSS to the browser page within your streaming software. ![Editing browser source](https://i.imgur.com/xCRea04.png)

While working with your custom CSS, turn on "Testing Mode" in Borderlands Twitch Integration's settings to display placeholders in the overlay each time it is refreshed.

It is recommended that you start by setting the Width and Height of the browser page to be the same as your stream's resolution; this ensures text will be rendered at full resolution, and if desired, allows you to position elements of the overlay freely using CSS absolute positioning. 

[See here for a list of basic CSS properties you might want to work with.](http://web.simmons.edu/~grabiner/comm244/weekthree/css-basic-properties.html)

Elements of the overlay may be selected in custom CSS:

| Element | Description |
| --- | --- |
| `body` | Apply properties such as font to all elements. |
| `.modifier` | The currently active modifier. |
| `.instructions` | The voting instructions. |
| `.timer` | The cycle countdown timer. |
| `.candidates` | The block containing the list of candidates. |
| `.candidate` | Each individual candidate within the list. |

An example of custom CSS that configures the overlay as seen in [this screenshot](https://i.imgur.com/a1TvvTQ.jpg):

```css
body {
    font: 48px "Gabriola";
    line-height: 1em;
}
.modifier:before {
    content: "Current modifier: ";
}
.modifier:after {
    content: ".";
}
.timer:before {
    content: "(";
}
.timer:after {
    content: ")";
}
```
