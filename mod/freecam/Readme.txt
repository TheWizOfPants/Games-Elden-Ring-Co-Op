Injectable camera for Elden Ring
============================
Camera version: 1.0.15
Camera credits: Otis_Inf.
----------------------------------------------------------------

   For updates and support: https://www.patreon.com/Otis_Inf
   For documentation, please visit: https://opm.fransbouma.com

----------------------------------------------------------------
CHANGES
============
v1.0.15:
    - Added: Hotsampling support. 

v1.0.14:
    - Fixed: Fixed for game patch 1.12 
    - Fixed: Time of Day in camera paths now works properly 

v1.0.13:
    - Added: Ability to configure which gamepad trigger is used for moving camera up/down 
    - Added: 3 camera position save slots (Ctrl-F1/F2/F3 to store, F1/F2/F3 to recall) when the camera is active. 
    - Added: Ability to configure which gamepad stick is used for rotating/moving the camera (for left-handed users). 
    - Added: Keybinding for appending a new node after the active node on the current path 
    - Added: Camera shake controls in both manual movement (for hand-shot videos) and camera paths. 
    - Added: Keybinding for deleting the current path 
    - Added: Support for the IGCS Connector 2.0+ for Reshade support per camera path node. 
    - Added: Keybinding for deleting the active node on the current path 
    - Added: Mouse sensitivity slider for people using high dpi mouse devices 
    - Added: Shift / Shift+Ctrl are now usable on the sliders to have them move slower and even more slower 
    - Added: The mousewheel can now be used on the sliders to move the value. 

v1.0.12:
    - Added: The ability to append a camera path node after the current node; both in the camera path window and using keybinds (Shift-F10) 

v1.0.11:
    - Changed: Applying the fast movement multiplier doesn't affect rotations anymore. 
    - Added: When closing the client when the game is still running, you're now asked whether you actually want to proceed. 

v1.0.10:
    - Fixed: Fixed for game version 1.0.5 

v1.0.9:
    - Added: Camera movement/rotation/fov interpolation factors. These factors can be used to make the camera movement/rotation/fov be interpolated over 
             multiple frames so you can get smooth camera movement, rotation and fov zoom in/out for videos without the need for camera paths. 
    - Added: Support for the IGCS Connector so you can create automated horizontal panoramas and lightfield screenshots. 

v1.0.8:
    - Added: Player-relative camera path playback has been added. This isn't 100% ideal tho: when crossing a cell in the world with your player, it will 
             display a single frame that likely looks off. This is unavoidable. 

v1.0.7:
    - Fixed: Fixed for game version 1.0.4 

v1.0.6:
    - Added: When the camera is enabled, the engine's dithering/transparency of objects near the camera is now disabled. 

v1.0.5:
    - Fixed: Fixed a game crash on Windows 11 or other situation where injecting the dll would cause the game to crash. 

v1.0.4:
    - Fixed: When opening the camera path window, the mouse cursor would disappear 

v1.0.3:
    - Changed: I finally found the real game pause function (the menu explanation pause), everything pauses perfectly: grass, no TAA blurriness. So the 
               addition added in 1.0.2 has been removed as it's no longer needed. Just press Numpad 0 to pause. 

v1.0.2:
    - Changed: The timestop wasn't ideal, due to the TAA mitigation causing physics issues. I decoupled these now, see below. 

v1.0.1:
    - Changed: Changed the timestop to a better pause. This freezes the engine better so it's not prone to random crashes. See below. 
    - Fixed: Mouse cursor vanished when it was over the camera path window 
    - Fixed: Higher LODs selector now doesn't crash the game anymore at random 
    - Fixed: Time of Day control didn't always work 

v1.0.0:
    - General: First version 


Features
===========
- Camera control: (Also in cut scenes)
	- FoV control
	- Free unlimited camera movement and rotation 
- Timestop / game pause control
- Camera paths support ('dolly cam') for defining moving camera trajectories for movies. 
- Game speed control (slow-motion, speed up)
- Frameskip
- HUD toggle
- Hotsampling (resize the game window to any resolution)
- Pillarbox/letterbox removal in custom aspect ratios (UW support)
- Vignette removal
- Configurable input interpolation for smooth camera movement/rotation/fov zoom in/out
- Chromatic Aberration (CA) removal
- Higher LODs
- Setting for being invisible to enemies
- Sun light direction control (pseudo Time of Day)
- Configurable keybindings
- Configurable gamepad buttonbindings

IMPORTANT
===========
You first have to disable anti-cheat. You can't use this camera in an online session, so you can't summon people. To disable anti-cheat, copy the file
steam_appid.txt, enclosed in the tools' zip file, to the folder where eldenring.exe is located, so the <game installation folder>\Game folder. 
Then start the game using the eldenring.exe in that folder directly, don't start the game via steam.

How to use
===========
After you've disabled the anti cheat, you can use the camera tools. 
Please do the following: Run the game and then the IGCSClient.exe. If the game runs as administrator, you have to run the 
IGCSClient.exe also as administrator, but this isn't required. In the IGCSClient, simply click 'Inject DLL'. If it hasn't found the 
eldenring.exe process, please click on the 'Select...' button to select it and then click 'Inject DLL'. 

Don't close the client, it's your tool to the camera for configuration
There's a Help tab in the GUI. Please read it. 

Camera control device
========================
In the configuration tab of the IGCS Client, you can specify what to use for controlling the camera: 
controller, keyboard+mouse, or both. The device you pick is blocked from giving input to the game, 
if you press 'Numpad .' (On by default). 

About Flawless Widescreen
==========================
When you use Flawless Widescreen the camera input key might not work or other elements might not work. They're not compatible. An UW fix is built into the tools, see
below

About MSI Afterburner
=====================
Using MSI Afterburner might cause problems with the camera tools (Crashing or Insert doesn't do anything). When that happens, disable MSI Afterburner.

About Game Pause and Motion blur
================================
To get rid of motion blur when the game is paused, disable it in the game settings.

About HUD toggle and Game Pause
=================================
It might be when you pause the game and hide the HUD, the compass is still partly visible. To hide that part, move the mouse a bit and then skip a frame.

About Ultra Wide Monitor support
================================
The tools fix the game's aspect ratio so it doesn't render the black bars when using an ultra-wide monitor. However this will only take effect
when you resize the resolution. So after you've injected the tools using the Inject DLL button, go to the game's system settings, and resize the resolution
of the game once. You can then click No afterwards to keep the one you had, and the game should now render in ultra-wide. As there's no hotsampling, you won't
have to do this again.

About hotsampling support
==========================
To take screenshots at higher resolutions than your regular gaming resolution, run the game in windowed mode. 
To get rid of the window border, on the Hotsampling tab, click 'Fake fullscreen'. 
To switch to a high resolution, select the resolution and aspect ratio you want from the tree on the Hotsampling tab and click 'Set'. 
You can also select one from the list of previous used resolutions if you switch between a given set of resolutions frequently. 
If the resolution fits your monitor, the game will add a border, you have to click 'Set' again to get rid of it. 

The IGCS client will resize the game window to the requested resolution and the game will resize the game 
framebuffer accordingly, allowing you to take a shot at a high resolution. To go back to your regular gaming 
resolution, simply click the 'Fake fullscreen' button again.

About 'Time of Day' support
============================
The time of day value of the game is stored in a pretty awkward way, with what looks like day values too and I didn't want to mess with that value at this point, as I don't
know what effect it has on the game world. As us photographers just want to change the sunlight and sky light anyway, the time of day support in the camera tools affect 
the sunlight direction only, based on the time you select. It's not ideal but it works for now.

About Higher LODs
==================
The tools offer a way to select higher level of detail (LODs). This is very taxing for the game tho, so expect massive performance degradation when using it, hence it should
only be used for shots. You might see some shadows appearing that shouldn't be there, in some cases. Use it with care. 

Have fun and create beautiful shots, m'kay? 

Cheers!

Otis_Inf