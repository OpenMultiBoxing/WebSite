# OpenMultiBoxing (Open Source, safe, Multiboxing)

This is an extension of the project started for World of Warcraft multiboxing ([WowOpenBox](https://WowOpenBox.org/)) but that applies to any kind of Windows game or app, including browser games.

Easiest: get it from the Microsoft Store, which installs and updates it for you (no Windows warning on first run):

<a href="https://apps.microsoft.com/detail/9n0dz59nl2dw"><img src="https://get.microsoft.com/images/en-us%20dark.svg" width="200" alt="Get it from Microsoft"/></a>

The Store version keeps its settings and profiles in `Documents\OpenMultiBoxing` (copy your `OpenMultiBoxingSettings*.tcl` files there to bring yours). It also puts there the `launchwow*.bat` files, to start several WoW windows at once without Battle.net, and [LaunchWoW.txt](https://github.com/OpenMultiBoxing/OpenMultiBoxing/blob/main/LaunchWoW.txt) which explains them.

Or download the [latest release](https://github.com/OpenMultiBoxing/OpenMultiBoxing/releases/latest) zip and see the [installation](https://github.com/OpenMultiBoxing/OpenMultiBoxing#installation) instructions. Version 11 needs its new exe: coming from an older version, extract the new zip in the same folder to keep your settings (auto update alone isn't enough, the older exe tells you so and keeps running your current version).

Use the Game menu to select your Game, or Game > "Add game window title..." to add your game's window title (the dialog shows which windows currently match; use `*` to match a changing part, e.g. a version number in the title).

Or check the Capture using foreground window option:

<p align="center">
<img src="https://wowopenbox.org/sshot_game_menu.PNG" alt="Game Menu screenshot">
</p>

<p align="center">
<img src="https://wowopenbox.org/sshot_capturefg.png" alt="Capture foreground screenshot">
</p>

You can then use the (configurable) hotkey `Ctrl-Shift-C` to capture whichever window you want.
After which your game name should be recorded in the Game menu and you can stick to normal Auto Capture (Options Menu).

OpenMultiboxing is known to work with:

- Blizzard Games (World of Warcraft, ...)
- EVE online
- Path of Exile
- Star Wars&trade;: The Old Republic&trade;
- Mir4
- Browser Games
- And pretty much any Windows 10 or 11 application...

And more... try and report your experience so we can add to this list!

Questions, suggestions, come on our <a href="https://discord.gg/SMGvEeb"><img src="discord.svg" alt="discord" align="center" height="24pt"></a>

Unlike WowOpenBox, which doesn't have any broadcasting capability, OMB since version 7 can **broadcast** any keys, any text/string (like your login password or a /command) as well left or right mouse clicks.

It can also do broadcasting across multiple PC connections since version 7.2.

<p align="center">
<a href="sshot11_0.png"><img src="sshot11_0.png" alt="OMB 11 screenshot (dark mode)"></a>
</p>

Recap of the main features:

- **Dark mode** (v11.0.0+): Option menu > Appearance: same as Windows (the default, follows it when you change it), light or dark. See the [help](https://OpenMultiBoxing.org/help#appearance-dark-mode).
- Window Layout wizard and manual tweaking; get your game windows exactly how you want them to be to play.
   - Save different layouts as profiles (File > New Profile...) and cycle through them with the Ctrl-Shift-L (next) and Ctrl-Shift-Alt-L (previous) hotkeys. Pick which profiles are in the rotation with Profile > "Profiles in rotation..." (all but Default by default).
- Any game or app: pick it in the Game menu or add its window title with Game > "Add game window title..." (use `*` to match a changing part, e.g. a version number in the title).
- Instant swapping of windows; with keyboard hotkeys for fast switching to the next or any specific window.
   - Change any hotkey in File > "Hotkeys...": click it and press the new key combination (right click clears it, Undo goes back).
- Left and right **mouse click broadcasting** option (press W or both buttons or hold them for more than half a second (delay configurable in settings) to avoid broadcasting)
   - For applications that do not support mouse events through PostMessage, uncheck "Mouse broadcast: message mode" in the Options menu.
- **Key broadcasting** when turned on, with exclusions (e.g W A S D for movement from main window)
   - Skip some windows (e.g. 4 and 5) from key and mouse broadcasting: check "Skip" and pick them in its dropdown, toggle with Ctrl-Shift-E.
   - **Rotate** (v11.3.0+): hold Right Shift and press a key several times to send it to one window after another (some call this round robin), e.g. to take turns with a stun. Also Rotate hotkeys and a Rotate bar (File > "Hotkeys..."). See the [help](https://OpenMultiBoxing.org/help#rotate).
   - Some applications/games do not accept PostMessage as a way to get input keys and you need to use OMB 5.2.7 with RoundRobin instead.
- **Key remap** you can change which key code is sent to the other windows.
- **Mirrors** (v10.0.0+): live, zoomable copies of an area of any game window (e.g. a bigger minimap, or the portraits of the small windows), anywhere on screen. File > "Mirrors...": "Add a mirror", click a window, drag the area; then drag to move, drag the sides to extend/shrink the area, mouse wheel to zoom, right click for options. Mirrors stay on their window as it gets swapped (or follow whichever window is main) and, outside of edit mode, act like that area of the window (v10.3.0+): mouse moves, all clicks and the mouse wheel go to the same place in it (right click option "Mouse goes to the source window", off for mirrors made with older versions: then mouse clicks go through the mirror). Mirrors can be see-through (right click > Opacity) and can focus their source window when clicked, or entered with focus follows mouse (right click option, off by default) (v11.1.0+). See the [help](https://OpenMultiBoxing.org/help#mirrors).
   - **Mirrored layout** (v10.1.0+): check "Mirrored" in Window Layout to stack all the game windows under the main one and show the other positions as live mirrors of them: instant swaps (no resizing), click a mirror to make that window main; mouse clicks and movement broadcasting reach the stacked windows. See the [help](https://OpenMultiBoxing.org/help#mirrored-layout).
- **Multi-PC** broadcasting: Select "Listen for other OMB connections" in the options menu on the main computer. Select "Connect to..." in the File menu on the other computers, type the main computer's name. On the main computer, accept the connection request from the other computers (default port is 4464, can be changed in settings).
   - The main window shows the network status: number of connected remote PCs on the main one, "Pause input from ..." checkbox on the remotes.
   - On a remote PC with no captured window, keys go to the system and the mouse is scaled to the primary monitor (full screen). With one window, keys, clicks and mouse movement go to that window. With several, keys and clicks are repeated in each window (mouse movement is ignored).
   - You also have the Option to send mouse movements also to remote PCs.
- Secure text (password) broadcasting option (can also broadcast slash commands, etc)
- Many additional options to switch which window your keys are going to:
  - Swap windows with hotkeys.
  - Focus follow mouse: turns on/off the Windows&trade; accessibility feature so you just hover a window to make it receive keys (instantly: OMB sets the hover delay to 0 ms, below the 100 ms minimum of the Windows slider)
  - Focus next/previous/specific windows with hotkeys.
- Free, OpenSource and the Safest option available.
- Online [help](https://OpenMultiBoxing.org/help), menus and tooltips on most UI element to help discovering features.

Note: key broadcasting replaces earlier round robin in OpenMultiBoxing (and WowOpenBox has no possibility of broadcasting, per Blizzard's multiboxing changes).
