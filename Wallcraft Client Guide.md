# WALLCRAFT GIGACHAD CLIENT SETUP GUIDE ™ 
Hey hey people, I've been putting off making a video so I've decided to make a text guide for the time being. Seeing as launch is coming up in just two weeks I'd better get on it.
This client setup guide goes through *ALL* the bells and whistles. If you think I've missed something cool, please share.
If you have any questions, concerns, or other feedback please let me know.

## SECTIONS/CHECKLIST:
### 1. [Initial Setup](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#1-initial-setup-1)
* Downloading, extracting the game 
* Changing realmlist 
* Deleting/Disabling WDB/cache 
* Extracting Wallcraft patches
### 2. [First Wave Troubleshooting](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#2-first-wave-troubleshooting-1)
* Known issues
* Data Execution Prevention exception for client mods
### 3. [ClientMods](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#3-client-mods)
* Nampower
* SuperWoW
* VanillaTweaks
* UnitXP_SP3
* VanillaHelpers
* PerfBoost
* Interact
* VanillaFixes
* DVXK
* Vanilla MultiMonitor Fix
### 4. [Addons](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#4-addons-1)
* Manual/Auto Installation
* Recommended Addons, and Lists
### 5. [Bonus Patches](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#5-bonus-patches-1)
* TBC Retexture
* Music Patch
* Blood Patch
* Sound Patches
### 6. [FAQ](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#6-faq-1)

## 1. INITIAL SETUP
### 1-A. DOWNLOAD/EXTRACT CLIENT
Any clean vanilla (1.12.1) client will do. We're going to be customizing it, so find a clean copy. You can download the client from [Wallcraft.org](https://www.wallcraft.org/), Archive.org or from other *standard* vanilla servers. ~~There's a tested [mini client](https://drive.usercontent.google.com/download?id=1Sk8DHceNFUKel2pn2MXFnzg0GSuo_AfN&export=download&authuser=0) if you'd like to save a little bit of space.~~ Wall's client is now very well minimized
Extract this to a folder you have rights to, such as a your desktop. Program files is *NOT* recommended as users don't have rights there.
I recommend renaming the folder to keep things tidy. Something like `Wallcraft`, I will be calling this `the Wallcraft folder` going forward.

### 1-B. CHANGE REALMLIST
In the root of the Wallcraft folder, there's a file `realmlist.wtf`. Changes the contents of this file to the code block below. Don't add any new lines, or any other information. 
`set realmlist wallcraft.org`

### 1-C. DELETE/DISABLE WDB FOLDER
Before playing on Wallcraft the `WDB` folder found in the Wallcraft folder must be deleted. Be sure to do this while there are no wow windows open, as the `WDB` folder is overwritten every time the game closes. The WDB folder contains cached information, and should be deleted regularly to allow updates to take full effect.
To disable the cache, create a file called `wdb.txt`, then rename it to `wdb` removing the `.txt`. The downside is more downloading, and possibly longer loading times but on the other hand you'd never have to clear your cache.

### 1-D. EXTRACT PATCHES
Download *ALL* the patches (.mpq files) from [Wallcraft.org](https://www.wallcraft.org/) after logging into the website, and extract them all to the `Data` folder in the Wallcraft folder.

## 2. FIRST WAVE TROUBLESHOOTING
Perform a first run of wow.exe, login, check your settings and see if you're running into any issues. Even if you're not running into any issues, you will need to do the steps in  2-E. Data Execution Prevention for client mods to work properly. Poor performance (lag, stuttering) maybe addressed by the client mods up next.
If your issue isn't covered here, be sure to bring it up in #general chat, or check #resources. Someone else might have a solution.

### 2-A. BLACK SCREEN BUG
> It launchs into a black screen, or the game's screen goes black when changing the video settings to Windowed/Fullscreen.

To fix this, you can change your settings file manually. Navigating from the Wallcraft folder its at `WTF/Config.wtf`
Change the relevant settings in the `Config.wtf` file to:
```
SET gxMaximize "1"
SET gxWindow "1"
```
Or simply download and extract this [zip](https://www.mediafire.com/file/ai0x81igceo06co/Blackscreen_Fix.zip/file) to your wow directory, overwriting.

### 2-B. Standard Vanilla Spells/Items Cached
> You start up the game and don't have new racial abilities, or common green items are bind on equip instead of not bound at all 

If this happens the `WDB` folder, in the Wallcraft folder needs to be deleted.
Be sure to do this while there are no wow windows open, as it is overwritten every time the client closes. This should be done again if you're running into any issues in the future. The WDB folder contains cached information, and should be deleted regularly to allow updates to take full effect.
To disable the cache, create a file called `wdb.txt`, then rename it to `wdb` removing the `.txt`. The downside is more downloading, and possibly longer loading times but on the other hand you'd never have to clear your cache.

### 2-C. Settings not saving
> Settings for things like video, interface, or addons don't persist between relaunches/game sessions. 

Torrent clients tend to make folders read-only when seeding, so you may need to stop your torrent client or remove the torrent. Afterwards, right click on the Wallcraft folder click on Properties and un-check the read only flag. Click Apply, and Okay.
When changing settings in game, be sure to log out or properly `/exit` to make sure your settings are saved. If you alt-f4, disconnect, or crash your settings may not be saved.

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
Make sure you check the [Section 2-E](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#2-e-doesnt-launchquickly-flashes-on-screen----data-execution-prevention) above to verify you have a Data Execution Prevention exception in place for these client mods.

### 3-A. [NamPower](https://gitea.com/avitasia/nampower/releases)
This mod is highly configurable, easing woes for casters with latency adding support for spell batching. Just extract the DLL into the same folder as your wow.exe
Also has an [addon](https://gitea.com/avitasia/NampowerSettings) to configure this mod in game with a menu opened from the minimap button. The addon allows visual indication of spell batching, with a movable icon (disabled by default). This  can be installed manually (extract to `Interface/Addons` and rename the folder to `NampowerSettings`), or automatically using the git addon manager. More information in [4. ADDONS](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#4-addons) section below.

### 3-B. [SuperWoW](https://github.com/balakethelock/SuperWoW/releases)
This mod does a lot. It adds sparkles on herbs/mines/chests. With the [addon](https://github.com/balakethelock/SuperAPI), it has a built in settings menu in the minimap button to change autoloot, FOV, noise in background, click through corpses and more. It also provides extra functionality to [supported addons](https://turtle-wow.fandom.com/wiki/Addons#SuperWoW_Addons).
Download, extract, and drop the DLL into the Wallcraft folder. SuperWoW's launcher isn't needed, and won't be used.
The MPQ patch is optional, but should be renamed `patch-S.MPQ` and moved to the `Data` folder in your wow directory if you're using it.
The [SuperAPI](https://github.com/balakethelock/SuperAPI) addon can be installed manually (extract to `Interface/Addons` and rename the folder to `SuperAPI`), or automatically using the git addon manager. More information in [4. ADDONS](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#4-addons) section below.

### 3-C. [VanillaTweaks](https://github.com/tubtubs/vanilla-tweaks/releases/)
VanillaTweaks has some features in common with SuperWow, but my fork doesn't touch these by default. This makes changes directly to the wow.exe, adding support for Farclip, frill distance, camera max distance, name player range, large address aware, camera skip glitch and some other stuff.
Simply extract the folder into your wow directory, and click and drag the WoW.exe ontop of VanillaTweaks.exe. This will create a new file `WoW_tweaked.exe` in the Wallcraft folder.

### 3-D. [UnitXP_SP3](https://codeberg.org/konaka/UnitXP_SP3/releases)
This client mod is very fresh, I don't have as much experience with it. It offers some improvements to name plate clipping, combat text rendering, and offers a means to disable weather effects as well as some other features. It adds some new keybinds, and lua calls that can line of sight check, distance check, behind check, and some tab targetting replacements that loop properly. Read more about all the functionality [here](https://codeberg.org/konaka/UnitXP_SP3/wiki)
Extract the DLL into the Wallcraft folder. You will also need to install the accompanying addon so that it can be configured in game from the minimap button. Extract the `UnitXP_SP3_Addon` folder to the `Interface/Addons` folder.

### 3-E. [VanillaHelpers](https://github.com/isfir/VanillaHelpers/releases)
Also very fresh. Makes some improvements to loading assets (useful for HD patches), screenshots saved as jpegs, allocating memory and adds lua functions for morphing/swapping display IDs and more. Check the [usage](https://github.com/isfir/VanillaHelpers?tab=readme-ov-file#usage) details for the lua here. Some addons take advantage of this mod's extended lua calls. For example, [MorphHelper](https://github.com/tubtubs/MorphHelper) adds a window and some slash commands for morphing.
Download the `VanillaHelpers.dll` and place it in the Wallcraft folder. This will need to be loaded by VanillaFixes, which is covered next.

### 3-F. [PerfBoost](https://gitea.com/avitasia/perf_boost)
This mod has many options and keybind toggles for when and what to hide/cull from rendering (players, units, corpses, spell effects). Just extract the DLL into the same folder as your wow.exe.
Also has an [addon](https://gitea.com/avitasia/PerfBoostSettings) to configure this mod in game with a menu opened from the minimap button. This  can be installed manually (extract to `Interface/Addons` and rename the folder to `PerfBoostSettings`), or automatically using the git addon manager. More information in [4. ADDONS](https://github.com/tubtubs/WoWClientSetupGuides/blob/main/Wallcraft%20Client%20Guide.md#4-addons) section below.

### 3-G. [Interact](https://github.com/luskanek/Interact)
Allows you to bind a key which you can then use to interact with the world around you. Can pick herbs, mine, or loot, skin, and talk to NPCs without using the mouse to target. 
Extract the entire zip to the same folder as your `wow.exe`, including the interface folder. You should enable this addon in game, and add the dll to the `dlls.txt`, which is coming up.

### 3-H. [VanillaFixes](https://github.com/hannesmann/vanillafixes/releases)
This is the launcher that will load the dlls on rum time. Extract the zip into your WoW folder.
In the wow folder you should now have a `dlls.txt`, open it and add the following lines to the bottom, for UnitSP_XP3 and VanillaHelpers, PerfBoost, and Interact support. The rest of the DLLs should be listed in there already.
```
# should be more DLLs listed above
# Add your own DLLs below
UnitXP_SP3.dll
VanillaHelpers.dll
perf_boost.dll
Interact.dll
```
Next, make a shortcut to VanillaFixes.exe. 
First, right click on VanillaFixes.exe and click `Create Shortcut`. Right click on the new shortcut, and click properties. Add `WoW_Tweaked.exe` after the quotes to the `Target` field. Click Apply, and Okay. Example: [(screenshot)](https://imgur.com/a/vanillafixes-shortcut-auWrnQq)
You can use this [icon](https://www.wallcraft.org/favicon.ico) for a Wallcraft icon. Click `Change Icon` in the properties window, then click browse  and navigate to the icon. Click Apply, then Okay. Feel free to click and drag the shortcut to your task bar, desktop, or whatever.

### 3-I. [DXVK](https://github.com/doitsujin/dxvk/releases)
DVXK is most useful for linux, and AMD graphics users. It can improve graphical performance by converting DirectX 9 calls to Vulkan. 
There's a release of [VanillaFixes](https://github.com/hannesmann/vanillafixes/releases) that includes DVXK, or a more update to date version can be downloaded from the [github repository](https://github.com/doitsujin/dxvk/releases).
Simply extract, and copy the 32bit d3d9.dll and dxgi.dll to your game folder, where WoW.exe may be found.

### 3-J. [Vanilla MultiMonitor Fix](https://github.com/Mates1500/VanillaMultiMonitorFix/releases)
I haven't used this myself, but it fixes some issues that come with having multiple monitors of various resolutions. I have multiple monitors of the same resolution/frequency and never ran into issues.
To install, extract the zip. You'll need to set `VMMFix_preferred_monitor.txt's` contents to your desired WoW monitor's index, as shown by running ShowAllDisplayDevices.exe. 
It's automatically setup to be loaded by VanillaFixes, so you should immediately be good to go after modifying that txt.

## 4. ADDONS
### 4-A. Manual Installation
Addons should be extracted to the `Interface/Addons` folder in the Wallcraft folder. If these folders don't exist, create them. If your addon isn't working, check that following is in place:
* The folder for the addon is named the same as the .toc file inside. (EG: `Interface\Addons\EmoteButtons` with `EmoteButtons.toc` inside)
* If there is no .toc file inside the addon folder, your addon may be in a deeper folder.
* If you're downloading from github, you'll likely need to remove the `-master` from the folder name, or just use the automated steps below.
### 4-B. Automated Installation - [GitAddonsManager](https://gitlab.com/woblight/GitAddonsManager/-/releases)
Simply download it and extract it to it's own folder. EG: `Wallcraft/GitAddonsManager`
Run `GitAddonsManager.exe` and point it to your addons directory (`Wallcraft/Interface/Addons` in the Wallcraft folder). If the `Interface/Addons` folders don't exist, create them. 
Click the + button near the top left and paste in a github/gitlab link and it will install automatically, renaming or moving folders as needed.
This manager can also update addons.
### 4-C. Setting up Addons in game
After logging in to your account, click the `Addons` button in the bottom left of the character selection screen.
Check off the boxes for the addons you'd like to enable/disable. In the upper right hand of the window set your addon memory to 0 (for no limit) or some high value like 512.
When configuring addons in game be sure to logout once you've made changes to ensure they save. If your client crashes, or your disconnect your settings will be lost.

### 4-D. Recommended Addons
* [PerfBoostSettings](https://gitea.com/avitasia/PerfBoostSettings) - Accompanying addon for PerfBoost, has many options for when and what to hide/cull from rendering (players, units, corpses, spell effects).
* [SuperAPI](https://github.com/balakethelock/SuperAPI) Mentioned above, it's the accompanying addon for SuperWoW that addons a mini map button to configure it's features.
* [NampowerSettings](https://gitea.com/avitasia/NampowerSettings) Mentioned above, configures the Nampower mod in game with a menu opened from the minimap button.

*UI OVERHAULS*
* [WC3 UI](https://github.com/Fiurs-Hearth/WIIIUI)
* [PFui](https://github.com/shagu/pfUI)
* [zUI](https://github.com/Ko0z/zUI) - PFui fork, complete UI replacement
* [ShaguTweaks](https://github.com/shagu/ShaguTweaks)
* [ShaguTweaks-extras](https://github.com/shagu/ShaguTweaks-extras)
* [ShaguTweaks-Mods](https://github.com/TokensWorth/ShaguTweaks-mods)
* [ShaguTweaks-More-Mods](https://github.com/CrimsonHollow/ShaguTweaks-more-mods)

*Conveniences*
* [BetterHelp](https://github.com/neolectron/BetterHelp) - `/help` now shows slash commands from ALL installed addons. Also can do `/sl` for slashcommand list.
* [SuperInspect](https://github.com/vakos1/SuperInspect) - Lets you keep inspecting, even if you've lost your target
* [FineZoom](https://github.com/Stormhand81/FineZoom)
* [Mail](https://github.com/Thrunk112/Mail)
* [PizzaSlices](https://github.com/neimad-mp/PizzaSlices) - PizzaSlices lets you create custom rings, fill them with various types of actions and bind them to different keys. Seems like emote buttons
* [EmoteButtonsV2](https://github.com/tubtubs/EmoteButtons) - Emotes, Macros, Slash commands from an expanding series of buttons
* [Parchment](https://github.com/tubtubs/Parchment) - Note taking
* [HatTrick](https://github.com/vakos1/HatTrick) - Adds checkboxes to the character screen for cloak and helm display toggling
* [AntiAFK](https://github.com/acid9000/AntiAfk) - Prevents AFK, especially useful for scanning AH
* [QuickBind](https://github.com/DennisWG/QuickBind) - Adds hoverbind
* [BonusScanner](https://github.com/jrc13245/BonusScanner)

*Aesthetics*
* [NosCursor](https://github.com/Beardedrasta/NosCursor) - Allows Customizing cursor
* [Aero](https://github.com/gashole/Aero) - Adds animation to frames
* [NewLevelFrame](https://github.com/alchem1ster/Vanilla-NewLevelFrame)
* [pfUI-fonts](https://github.com/shagu/pfUI-fonts)
* [NameChangeScript](https://github.com/zirtox1992/NameChangeScript)
* [ShaguWidget](https://github.com/shagu/ShaguWidget)
* [Extended Quest Log](https://github.com/laytya/EQL3)
* [BizzMo](https://github.com/Dyaxler/BlizzMo_Vanilla) - Allows you to move blizzard frames 

*Automation*
* [LazyPig](https://github.com/ProKlutch/LazyPig) - The old standy for lots of automation, less efficient than newer addons though.
* [EasyLoot](https://github.com/MarcelineVQ/EasyLoot) - SuperWoW compliant, implements features from LazyPig (but more efficient) 
* [QuestRepeat](https://github.com/MarcelineVQ/QuestRepeat) SuperWoW compliant, implements fast quest turn in from LazyPig (but more efficient) 
* [DisableEscape](https://github.com/EinBaum/DisableEscape) - Prevents escape from closing summons, and invites
* [Automaton](https://gitlab.com/Artur91425/Automaton)

*Combat/Raiding*
* [SP SwingTimer (SuperWoW support)](https://github.com/MarcelineVQ/SP_SwingTimer)
* [Cursive](https://github.com/pepopo978/Cursive) - Features for more efficient curse/debuff application, adds slash commands and tracking bars. Requires SuperWoW
* [Decursive](https://github.com/MarcelineVQ/Decursive)
* [Rinse](https://github.com/Otari98/Rinse) - Decursive, but more efficient and supporting client mods 
* [ShaguDPS](https://github.com/shagu/ShaguDPS)
* [AutoMana+](https://github.com/TheRealFayz/AutoManaPlus) - Automatically consume potions and more
* [GrimReaper](https://github.com/xorann/GrimReaper) - Shows the last 3 hits before you died
* [MiksScrollingCombatText](https://github.com/AtheneGenesis/Vanilla_MikScrollingBattleText)* [1](https://github.com/pepopo978/Vanilla_MikScrollingBattleText)

*Crafting*
* [AdvancedTradeSkillWindow2](https://github.com/Shellyoung/AdvancedTradeSkillWindow2)
* [Crafty](https://github.com/shirsig/crafty) - Adds search bar to crafting window
* [RecipeRadar](https://github.com/laytya/RecipeRadar-vanilla)
* [MissingCrafts](https://github.com/refaim/MissingCrafts)
* [FishingBuddy](https://github.com/SeVeN7000/FishingBuddy)* [1](https://github.com/ilithyia-addons/FishingBuddy)
* [FishInfo2](https://github.com/wbb1977/FishInfo2)

*Economy*
* [Aux (auctions)](https://github.com/acid9000/Aux-addon)* [1](https://github.com/shirsig/aux-addon-vanilla)
* [Accountant](https://github.com/wow-vanilla-addons/Accountant)

*Frames and Plates*
* [kUI-Namaplates](https://github.com/laytya/Kui-Namaplates) - Configurable name plates
* [TankPlates](https://github.com/MarcelineVQ/TankPlates) - SuperWoW compatible name plates, modifies unit's plates that aren't attacking you for easier tanking

*Inventory*
* [MrPlow](https://github.com/McPewPew/MrPlow)
* [BagShui](https://github.com/Skillkrote/Bagshui)

*Macros*
* [AntiSpamStopCast](https://github.com/thepparker/AntiSpamStopCast)
* [NoToggle](https://github.com/shirsig/notoggle) - Disables the toggling of auto attack
* [Attack](https://github.com/shirsig/attack) - Enables /attack command
* [MacroTT-V](https://github.com/UndercityAddons-Vanilla/MacroTT-V) - Adds tooltips to macros using new slash commands

*Map*
* [Yatlas](https://github.com/Rumchiller/EM_Yatlas) - Minimap data based map, has many markers for graveyards, dungeons, and other points of interest
* [ModernMapMarkers-Vanilla](https://github.com/Drakensangs/ModernMapMarkers-Vanilla) - Adds map markers for many common points of interests (dungeons, graveyards, towns, etc)
* [Atlas](https://github.com/laytya/Atlas) - Dungeon maps, and loot tables

*Questing/Gathering/Farming*
* [pfQuest](https://github.com/shagu/pfQuest)
* [pfQuest-icons](https://github.com/shagu/pfQuest-icons)
* [SoloRaidTargetIcons (Requires SuperWoW)](https://github.com/refaim/SoloRaidTargetIcons)
* [UnitScan-Vanilla](https://github.com/shirsig/unitscan-vanilla)
* [ShaguScan](https://github.com/shagu/ShaguScan)
* [GrindSpots](https://github.com/onnateldome/GrindSpots)
* [MobsToLevel](https://github.com/idontbyte/MobsToLevel)
* [Estimated Time to Level](https://github.com/shirsig/ETL)

*Silly*
* [Comix](https://github.com/Cysthen/Comix)
* [ChickenJockey](https://github.com/SwizzPop/ChickenJockey)
* [DrunkTracker](https://github.com/akzkak/DrunkTracker)
* [MorphHelper](https://github.com/tubtubs/MorphHelper) - Window, and slash commands for VanillaHelper's morph commands

*Social*
* [WIM](https://github.com/me0wg4ming/WIM)
* [Friend-O-Tron](https://github.com/refaim/Friend-O-Tron) - Sync friend lists among toons on the same server

*Buffs
* [DoiteAuras](https://github.com/Player-Doite/DoiteAuras) - WeakAuras for VanillaWoW? Requires Nampower and UnitXP_SP3

Big addon lists:
* [Everlook](https://forum.everlook.org/t/list-of-github-addons/18)
* [Github Big Repo of Addons](https://github.com/ericraio/vanilla-wow-addons/)
* [TurtleWoW](https://turtle-wow.fandom.com/wiki/Addons#Full_Addons_List)
* [TurtleWoW - SuperWoW Compatible Addons](https://turtle-wow.fandom.com/wiki/Addons#SuperWoW_Addons)

## 5. BONUS PATCHES
###  [TBC Texture Pack](https://mega.nz/file/4YtVlBZL#lwFFaaDEauWIZd0sW53gz8J0dyo_EhmnSsRvaclRwpA)
This is an old pack, don't recall the original author. It replaces some vanilla textures mostly for buildings and ground with TBC textures.
### [Old World Music Rescore](https://www.mediafire.com/file/017h0k7sgdlwlg4/Wallcraft_OldWorld_Rescore.zip/file)
This is a custom ported music pack from future expansions. Tuned for Wallcraft.

Extract both these patches, and rename them `Patch-Z.mpq` and `Patch-X.mpq`, and move them to your `Data` folder in the Wallcraft folder.
Be sure to rename them first so they don't overwrite any of Wallcraft's patches. You may need to delete the `WDB` folder for these extra patches to take effect.
### [Blood Mod](https://drive.google.com/file/d/1dtNAsN4DbB05ZRO7jVWt6gfDe79pxeDW/view)
Just download and extract to the `Data` folder in your Wallcraft folder. This is called `Patch-Y.mpq` which shouldn't conflict with any other patches. Note, it might cause poor performance during raids.

### [Intra's water patch](https://discord.com/channels/407664041016688662/1264693803395059742)
Imo the lighting isnt as good and its very transparent, but the animation looks very pretty.
Could look into modding lightingparams.dbc to make it less transparent.
[Mirror Link](https://www.mediafire.com/file/nlq456dkmmmkcym/patch-W.mpq/file)
You just need to move this .mpq file to the `Data` folder.

### [NoErrorSounds](https://github.com/Macumbafeh/NoErrorSounds/)
Disables error sounds, in particular the spell fizzles when spamming.
Download and extract to the `Sound` folder to the same folder as your wow.exe

### [FishPing](https://github.com/notsureawake/FishPing)
Makes the sound when a fish is on the line a lot more noticable. Adapted from another expansion, using new path but same sound.
Download and extract to the `Sound` folder to the same folder as your wow.exe

### [Classic-Snowfall](https://github.com/Linae-Kronos/Classic-Snowfall)
Something about keybinds firing on "Key up" instead of "Key down", its an improvement I suppose.
If you use pfUI's actionbars, simply enable the option "Actionbar -> General -> Trigger Actions On Key Down". 
If you're not using pfUI's actionbars, then install the [Classic-Snowfall](https://github.com/Linae-Kronos/Classic-Snowfall) addon.

* [More Sound Mods](https://turtle-wow.fandom.com/wiki/Sound_Mods)
* [Turtle WoW Client Mods](https://turtle-wow.fandom.com/wiki/Client_Mods) - Many of these are designed for turtle wow, but you might have success using some here.

### Other Patches
Darker nights isn't currently supported, it will cause crashes in new zones added in Wallcraft (like Dalaran). I've heard rumor that Wall is planning on building Darker nights directly into Wallcraft on Launch. I'm not aware of, or interested in supporting any HD model packs. I've heard rumor of a nude patch, I may one day acquire this for myself... Purely for *very interesting* scientific purposes of course.
[ImpulseBooster](https://github.com/Warlockbugs/impulse-booster) - I personally don't recommend it, it caused issues for me without any performance gain. Apparently it works better for TBC or WOTLK.

## 6. FAQ
* I don't have a threat meter to recommend. Consult your raid leader, or fellow raiders for a tested, trusted meter.

TODO:
* [PerfBoost](https://gitea.com/avitasia/perf_boost) - Performance boosting mod, accompanying [addon](https://gitea.com/avitasia/PerfBoostSettings)
* [FishPing](https://gitea.com/avitasia/PerfBoostSettings)
* [SuperWoW-Patch](https://github.com/turtlenips/superwow-patch) - Fixes the hex values from superwows healing in scbt? I think nampower fixes this actually
* 

* [pfUI-AddonSkinner](https://github.com/jrc13245/pfUI-addonskinner)
* [no1600x1200](https://turtle-eu.b-cdn.net/client/0DF2274116278E8330DD7069902B642F1A83F33FEFD909807A22EDA197D88652/no1600x1200.dll) - Might be replaceable with the multimonitor fix, could be preferable since the source is lost