# ASHEN WOW GIGACHAD CLIENT SETUP GUIDE ™ 
Hey hey people, I've been putting off making a video so I've decided to make a text guide for the time being
This client setup guide goes through *ALL* the bells and whistles for the standard vanilla 1.12.1 client. I will not be covering ANYTHING for the 1.14 clients, proxies, or their addons.
This guide is for Windows (or doesn't cover much about linux). Check out the [pinned post](https://discord.com/channels/1412156063788040214/1436766972896477204/1436767564800725002) in #🐧-wow-on-linux if you need assistance with linux
With that in mind, if you think I've missed something cool, please share.
If you have any questions, concerns, or other feedback please let me know.

## SECTIONS/CHECKLIST:
### 1. [Initial Setup](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#1-initial-setup-1)
* Downloading, extracting the game
* Changing realmlist
* Deleting/Disabling WDB/cache
### 2. [First Wave Troubleshooting](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#2-first-wave-troubleshooting-1)
* Known issues
* Data Execution Prevention exception for client mods
### 3. [ClientMods](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#2-first-wave-troubleshooting-1)
* Nampower
* SuperWoW
* VanillaTweaks
* UnitXP_SP3
* VanillaHelpers
* VanillaFixes
* DVXK
* Vanilla MultiMonitor Fix
### 4. [Addons](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#2-first-wave-troubleshooting-1)
* Manual/Auto Installation
* Recommended Addons, and Lists
### 5. [Bonus Patches](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#5-bonus-patches-1)
* TBC Retexture
* Music Patch
* Blood Patch
* Water Patch
* Darker Nights
### 6. [FAQ](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#6-faq-1)

## 1. INITIAL SETUP

### 1-A. DOWNLOAD/EXTRACT CLIENT
Any clean vanilla (1.12.1) client will do. We're going to be customizing it, so find a clean copy. You can download the [TinyWallClient](https://shorturl.at/oQmjW), a 1.12.1 client from Archive.org or from a *standard* vanilla server.
Extract this to a folder you have rights to, such as a your desktop. Program files is *NOT* recommended as users don't have rights there.
I recommend renaming the folder to keep things tidy. Something like `WoW`, I will be calling this `the WoW folder` going forward. I may accidentally call it `the Wallcraft folder`, as this guide was originally written for Wallcraft.

### 1-B. CHANGE REALMLIST
In the root of the WoW folder, there's a file `realmlist.wtf`. Changes the contents of this file to the code block below. Don't add any new lines, or any other information. 
```set realmlist ashen-wow.space```

### 1-C. DELETE/DISABLE WDB FOLDER
Before playing on Ashen WoW the `WDB` folder found in the WoW folder should be deleted. Be sure to do this while there are no wow windows open, as the `WDB` folder is overwritten every time the game closes. The WDB folder contains cached information, and should be deleted regularly to allow updates to take full effect.
To disable the cache, create a file called `wdb.txt`, then rename it to `wdb` removing the `.txt`. The downside is more downloading, and possibly longer loading times but on the other hand you'd never have to clear your cache.

## 2. FIRST WAVE TROUBLESHOOTING
Perform a first run of wow.exe, login, check your settings and see if you're running into any issues. Even if you're not running into any issues, you will need to do the steps in  [2-E. Data Execution Prevention](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#2-e-doesnt-launchquickly-flashes-on-screen----data-execution-prevention) for client mods to work properly. Poor performance (lag, stuttering) maybe addressed by the client mods up next.
If your issue isn't covered here, be sure to bring it up in #🤝-help-general. Someone else might have a solution.

### 2-A. BLACK SCREEN BUG
> It launchs into a black screen, or the game's screen goes black when changing the video settings to Windowed/Fullscreen.

To fix this, you can change your settings file manually. Navigating from the WoW folder its at `WTF/Config.wtf`
Change the relevant settings in the `Config.wtf` file to:
```
SET gxMaximize "1"
SET gxWindow "1"
```
Or simply download and extract this [zip](https://www.mediafire.com/file/ai0x81igceo06co/Blackscreen_Fix.zip/file) to your wow directory, overwriting.

### 2-B. Settings not saving
> Settings for things like video, interface, or addons don't persist between relaunches/game sessions. 

Torrent clients tend to make folders read-only when seeding, so you may need to stop your torrent client or remove the torrent. Afterwards, right click on the WoW folder click on Properties and un-check the read only flag. Click Apply, and Okay.
When changing settings in game, be sure to log out or properly `/exit` to make sure your settings are saved. If you alt-f4, disconnect, or crash your settings may not be saved.

### 2-C. Standard Vanilla Spells/Items Cached
> You start up the game and see stats on items for a different patch 

If this happens the `WDB` folder, in the WoW folder needs to be deleted.
Be sure to do this while there are no wow windows open, as it is overwritten every time the client closes. This should be done again if you're running into any issues in the future. The WDB folder contains cached information, and should be deleted regularly or disabled to allow updates to take full effect.
To disable the cache, create a file called `wdb.txt`, then rename it to `wdb` removing the `.txt`. The downside is more downloading, and possibly longer loading times but on the other hand you'd never have to clear your cache.

### 2-D. Reset Settings Popup/Doesn't Launch
> Hardware changed. Reload default settings? Popup
> Doesn't launch

You can always click no to this popup, but sometimes it draws in the background and it may just appear that wow isnt launching at all. You can see the popup in task manager (wow.exe, but very low memory usage less than 30mb) to confirm this is happening.
This popup is caused by launching a different expansion of wow (Wrath, cataclysm, whatever).
Sometimes you can get the popup to draw properly if you launch the game from the game folder (rather than a shortcut on desktop, or taskbar).
If this doesn't work, you can safely [delete the registry keys](https://www.revouninstaller.com/blog/how-to-edit-delete-and-create-registry-keys/) stored at `HKCU\Software\Blizzard Entertainment\World of Warcraft\Client` and then launch without issue.

### 2-E. Doesn't Launch/Quickly Flashes on Screen  - [Data Execution Prevention](https://github.com/balakethelock/SuperWoW?tab=readme-ov-file#troubleshooting)
> quickly flashes on screen
> doesn't launch at all

This relates more to client mods, which will be covered in the next section. Client mods often inject code, which can be flagged by windows services as malicious, so Windows likes to stop them from running. This Data Execution Prevention setting needs to be disabled for your wow, but should still be enabled globally for security.
The easiest way to access this setting is to search `Advanced System Settings` in the search bar, click on `Settings` in the `performance` section, and then navigate to the `Data Execution Tab` at the top. The most secure setting would be to turn on for all programs, and make an exception for your wow.exe.
[Screenshots](https://imgur.com/a/dep-data-execution-prevention-exception-L70Xeom)
NOTE: The exception setting needs to be re-applied if you ever move your wow install to another directory.

### 2-F. Popup on Launch "Needs to a valid 1.6-1.12.1 client" (paraphrasing, havent seen this in a while) from VanillaFixes
If it was working properly before it'll often work properly on 2nd try, or after a reboot. If the issue persists, check the antivirus to see if any of the client mod DLLs (nampower, vfpatcher, superwow, UnitXP_SP3) got flagged as malicious or quarantined.

## 3. CLIENT MODS
Make sure you check the [2-E. Data Execution Prevention](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#2-e-doesnt-launchquickly-flashes-on-screen----data-execution-prevention) section above to verify you have a Data Execution Prevention exception in place for these client mods.

### 3-A. [NamPower](https://gitea.com/avitasia/nampower/releases)
This mod eases woes for casters with latency. It also adds support for spell batching. Just extract the DLL into the same folder as your wow.exe

### 3-B. [SuperWoW](https://github.com/balakethelock/SuperWoW/releases)
This mod does a lot. It adds sparkles on herbs/mines/chests. With the [addon](https://github.com/balakethelock/SuperAPI), it has a built in settings menu in the minimap button to change autoloot, FOV, noise in background, click through corpses and more. It also provides extra functionality to [supported addons](https://turtle-wow.fandom.com/wiki/Addons#SuperWoW_Addons).
Download, extract, and drop the DLL into the WoW folder. SuperWoW's launcher isn't needed, and won't be used.
The MPQ patch is optional, but should be renamed `patch-S.MPQ` and moved to the `Data` folder in your wow directory if you're using it.
The [SuperAPI](https://github.com/balakethelock/SuperAPI) addon can be installed manually (extract to `Interface/Addons` and rename the folder to `SuperAPI`), or automatically using the git addon manager. More information in [4. ADDONS](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Ashen%20Client%20Guide.md#4-addons-1) section below.

### 3-C. [VanillaTweaks](https://github.com/tubtubs/vanilla-tweaks/releases/)
VanillaTweaks has some features in common with SuperWow, but my fork doesn't touch these by default. This makes changes directly to the wow.exe, adding support for Farclip, frill distance, camera max distance, name player range, large address aware, camera skip glitch and some other stuff.
Simply extract the folder into your wow directory, and click and drag the WoW.exe ontop of VanillaTweaks.exe. This will create a new file `WoW_tweaked.exe` in the WoW folder.

### 3-D. [UnitXP_SP3](https://codeberg.org/konaka/UnitXP_SP3/releases)
This client mod is very fresh, I don't have as much experience with it. It offers some improvements to name plate clipping, combat text rendering, and offers a means to disable weather effects as well as some other features. IT adds some neat lua calls that can line of sight check, distance check, behind check, and some tab targetting replacements that loop properly. Read more about all the functionality [here](https://codeberg.org/konaka/UnitXP_SP3/wiki)
Extract the DLL into the Wallcraft folder. You will also need to install the accompanying addon so that it can be configured in game from the minimap button. Extract the `UnitXP_SP3_Addon` folder to the `Interface/Addons` folder.

### 3-E. [VanillaHelpers](https://github.com/isfir/VanillaHelpers/releases)
Also very fresh. Makes some improvements to loading assets, allocating memory and adds lua functions for morphing/swapping display IDs and more. Check the [usage](https://github.com/isfir/VanillaHelpers?tab=readme-ov-file#usage) details for the lua here. I don't know of any addons that take advantage of this yet.
Download the `VanillaHelpers.dll` and place it in the WoW folder. This will need to be loaded by VanillaFixes, which is covered next.

### 3-F. [VanillaFixes](https://github.com/hannesmann/vanillafixes/releases)
This is the launcher that will load the dlls on run time. Extract the zip into your WoW folder.
In the wow folder you should now have a `dlls.txt`, open it and add the following lines to the bottom, for UnitSP_XP3 and VanillaHelpers support. The rest of the DLLs should be listed in there already.
```
# should be more DLLs listed above
# Add your own DLLs below
UnitXP_SP3.dll
VanillaHelpers.dll
```
*NOTE: Technically the shortcut isn't necessary for Ashen WoW, but maybe for other servers*
*On Ashen you can rename your `wow.exe` to `wow.exe.old` then rename `wow_tweaked.exe` to `wow.exe`, then going forward use the launcher/loader `vanillafixes.exe` to start wow*
Next, make a shortcut to VanillaFixes.exe. 
First, right click on VanillaFixes.exe and click `Create Shortcut`. Right click on the new shortcut, and click properties. Add `WoW_Tweaked.exe` after the quotes to the `Target` field. Click Apply, and Okay. Example: [(screenshot)](https://imgur.com/a/vanillafixes-shortcut-auWrnQq)
If there's a cool Ashen Icon, you can download that. Click `Change Icon` in the properties window, then click browse  and navigate to the icon. Click Apply, then Okay. Feel free to click and drag the shortcut to your task bar, desktop, or whatever.

### 3-G. [DXVK](https://github.com/doitsujin/dxvk/releases) (optional / only if you need it)
DVXK is most useful for linux, and AMD graphics users. It can improve graphical performance by converting DirectX 9 calls to Vulkan. 
There's a release of [VanillaFixes](https://github.com/hannesmann/vanillafixes/releases) that includes DVXK, or a more update to date version can be downloaded from the [github repository](https://github.com/doitsujin/dxvk/releases).
Simply extract, and copy the 32bit d3d9.dll and dxgi.dll to your WoW folder.

### 3-H. [Vanilla MultiMonitor Fix](https://github.com/Mates1500/VanillaMultiMonitorFix/releases) (optional / only if you need it)
I haven't used this myself, but it fixes some issues that come with having multiple monitors of various resolutions. I have multiple monitors of the same resolution/frequency and never ran into issues.
To install, extract the zip. You'll need to set `VMMFix_preferred_monitor.txt's` contents to your desired WoW monitor's index, as shown by running `ShowAllDisplayDevices.exe`. 
It's automatically setup to be loaded by VanillaFixes, so you should immediately be good to go after modifying that txt.

## 4. ADDONS
### 4-A. Manual Installation
Addons should be extracted to the `Interface/Addons` folder in the WoW folder. If these folders don't exist, create them. If your addon isn't working, check that following is in place:
* The folder for the addon is named the same as the .toc file inside. (EG: `Interface\Addons\EmoteButtons` with `EmoteButtons.toc` inside)
* If there is no .toc file inside the addon folder, your addon may be in a deeper folder.
* If you're downloading from github, you'll likely need to remove the `-master` from the folder name, or just use the automated steps below.
### 4-B. Automated Installation - [GitAddonsManager](https://gitlab.com/woblight/GitAddonsManager/-/releases)
Simply download it and extract it to it's own folder. EG: `WoW/GitAddonsManager`
Run `GitAddonsManager.exe` and point it to your addons directory (`WoW/Interface/Addons` in the WoW folder). If the `Interface/Addons` folders don't exist, create them. 
Click the + button near the top left and paste in a github/gitlab link and it will install automatically, renaming or moving folders as needed.
This manager can also update addons.
### 4-C. Setting up Addons in game
After logging in to your account, click the `Addons` button in the bottom left of the character selection screen.
Check off the boxes for the addons you'd like to enable/disable. In the upper right hand of the window set your addon memory to 0 (for no limit) or some high value like 256.
When configuring addons in game be sure to logout once you've made changes to ensure they save. If your client crashes, or your disconnect your settings will be lost.

If you're running into issues with addons, feel free to reach out in the #💾-addons-help channel. Someone may be able to help you out

### 4-D. Recommended Addons
[SuperAPI](https://github.com/balakethelock/SuperAPI) Mentioned above, it's the accompanying addon for SuperWoW that addons a mini map button to configure it's features.
*UI OVERHAULS*
[PFui](https://github.com/shagu/pfUI)
[ShaguTweaks](https://github.com/shagu/ShaguTweaks)
[WC3 UI](https://github.com/Fiurs-Hearth/WIIIUI)

*Conveniences*
[pfQuest](https://github.com/shagu/pfQuest)
[pfQuest-icons](https://github.com/shagu/pfQuest-icons)
[Accountant](https://github.com/wow-vanilla-addons/Accountant)
[RecipeRadar](https://github.com/laytya/RecipeRadar-vanilla )
[Atlas](https://github.com/laytya/Atlas)
[Mail](https://github.com/Thrunk112/Mail)
[LazyPig](https://github.com/ProKlutch/LazyPig) 
[Crafty](https://github.com/shirsig/crafty) - Adds search bar to crafting window
[BagShui](https://github.com/Skillkrote/Bagshui)
[Aux (auctions)](https://github.com/shirsig/aux-addon-vanilla)
[EmoteButtonsV2](https://github.com/tubtubs/EmoteButtons) - Emotes, Macros, Slash commands from an expanding series of buttons
[ShaguDPS](https://github.com/shagu/ShaguDPS)
[SP SwingTimer (SuperWoW support)](https://github.com/MarcelineVQ/SP_SwingTimer)
[SoloRaidTargetIcons (Requires SuperWoW)](https://github.com/refaim/SoloRaidTargetIcons)
[Parchment](https://github.com/tubtubs/Parchment) - Note taking
[TankPlates](https://github.com/MarcelineVQ/TankPlates)
[WIM](https://github.com/me0wg4ming/WIM)

*Silly*
[Comix](https://github.com/Cysthen/Comix)

Big addon lists:
[Everlook](https://forum.everlook.org/t/list-of-github-addons/18)
[Github Big Repo of Addons](https://github.com/ericraio/vanilla-wow-addons/)
[TurtleWoW](https://turtle-wow.fandom.com/wiki/Addons#Full_Addons_List)
[TurtleWoW - SuperWoW Compatible Addons](https://turtle-wow.fandom.com/wiki/Addons#SuperWoW_Addons)

## 5. BONUS PATCHES
###  [TBC Texture Pack](https://mega.nz/file/4YtVlBZL#lwFFaaDEauWIZd0sW53gz8J0dyo_EhmnSsRvaclRwpA)
This is an old pack, don't recall the original author. It replaces some vanilla textures mostly for buildings and ground with TBC textures.
### [Old World Music Rescore](https://www.mediafire.com/file/m0m5xrg9qsqu4pp/Vanilla_OldWorld_Rescore.zip/file)
This is a custom ported music pack from future expansions. Tuned for Vanilla WoW.

Extract both these patches, and rename them `Patch-A.mpq` and `Patch-X.mpq`, and move them to your `Data` folder in the WoW folder.
Be sure to rename them first so they don't overwrite any of default patches. You may need to delete the `WDB` folder for these extra patches to take effect.
### [Blood Mod](https://drive.google.com/file/d/1dtNAsN4DbB05ZRO7jVWt6gfDe79pxeDW/view)
Just download and extract to the `Data` folder in your WoW folder. This is called `Patch-Y.mpq` which shouldn't conflict with any other patches. Note, it might cause poor performance during raids.
### [Intra's water patch](https://discord.com/channels/407664041016688662/1264693803395059742)
Imo the lighting isnt as good and its very transparent, but the animation looks very pretty.
Could look into modding lightingparams.dbc to make it less transparent.
[Mirror Link](https://www.mediafire.com/file/nlq456dkmmmkcym/patch-W.mpq/file)
You just need to move this .mpq file to the `Data` folder.
### [Darker Nights](https://www.ownedcore.com/forums/world-of-warcraft/world-of-warcraft-model-editing/599581-dark-nights-mod-vanilla-1-12-1-a.html)
You just need to move this .mpq file to the `Data` folder.

### Other Patches
I'm not aware of, or interested in supporting any HD model packs. I've heard rumor of a nude patch, I may one day acquire this for myself... Purely for *very interesting* scientific purposes of course.

## 6. FAQ
* I don't have a threat meter to recommend. Consult your raid leader, or fellow raiders for a tested, trusted meter.