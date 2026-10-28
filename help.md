# Open MultiBoxing online HELP

_Note that this page isn't fully updated yet and is still more or less the original WowOpenBox help._

## Basic information
![Window Layout](https://wowopenbox.org/sshotWindowLayout.png)

1. Use the "Window Layout" UI to setup your Windows automatically. And you can tweak the intelligent auto layouts by:
    + Dragging any window to reposition it
    + Resize it by dragging the orange bottom right corner
    + Toggle "Stay on top" by clicking on the text
    + Use the snap to grid feature to constraint the position
    + Use the arrow keys for precise movement by 1 pixel

1. _and/or tweak it using:_ Manual Setup (from main window):

    1. Manually select the Size you want your next window to be(*)

    1. Manually select the position you want it to be at(*)

    1. Decide if that window should stay on top of others. you can use a hotkey (default `Ctrl-Shift-T`) to toggle that setting on the fly.(*)

1. Use the Bnet launcher to start your wow windows so you don't need to type your password, OMB will make them borderless automatically for you, but check in game resolution options to avoid pixelization (100% Render Scale, Correct window size). See also the `.bat` files included in the OMB zip file for a way to start multiple games windows at once (but you'll need to enter credentials individually or through the Secure copy paste broadcasting dialog).

1. OMB since version 4.1 will automatically capture and place the windows in their respective position for you (you can turn that option off in the Option menu). Otherwise, press the "Capture" button or use its hotkey (default `Ctrl-Shift-C`). If you want to manage other games than World of Warcraft, see the ['Other Games' section below](#other-games)

1. Press a hotkey to change which window gets the keyboard input: default key are `Ctrl-F1` for Wow 1, `Ctrl-F2` for Wow 2, etc.. or rotate between windows with hotkeys to focus the next window (defaults to `Ctrl-Shift-N`) and previous window (defaults to `Ctrl-Shift-P`). Hotkeys can be changed in File > "Hotkeys..." (see [below](#hotkeys)).

1. Press a hotkey to bring window N to the main (1) window: default `Ctrl-Shift-F2` will swap 1 and 2,  `Ctrl-Shift-F3` for swapping 1 and 3, etc... Or rotate the swap between all windows by repeatedly pressing `Ctrl-~` for forward swap or `Ctrl-Shift-~` for backward swap.

1. You can toggle the overlay on/off at any time using the default hotkey `Ctrl-Shift-O` or the checkbox on the main window.

1. If you want to use the optional key **broadcasting**, `Ctrl-Shift-R` is the default hotkey to toggle it on/off. Enter which keys should be excluded from broadcasting in the entry box (default is all keys are broadcasted except for W S A D, see the [FAQ entry](https://github.com/WowOpenBox/WowOpenBox/wiki/FAQ#what-special-key-names-can-i-use-in-the-round-robin-key-list) for complete list of special key names).

1. You can remap keys, so if you press say `F` in the current main window, `T` is sent to others, by addding `F:T` in the key remapping section of the UI.

1. You can **skip** some windows from key and mouse click broadcasting (e.g. keep OMB 4 and 5 out of it): check "Skip" and pick the windows in its dropdown. Once windows are picked, `Ctrl-Shift-E` toggles between broadcasting to all windows and skipping them. The skip follows the window, not its position, so a skipped window swapped into the main spot still gets nothing broadcast.

1. **Profiles**: save different setups, for instance one per window layout (a big main window with smaller ones vs. a full screen main window), with File > "New Profile...", then change the Window Layout and "Save and Apply". Switch between them in the Profile menu or cycle through them with `Ctrl-Shift-L` (next) and `Ctrl-Shift-Alt-L` (previous). Profile > "Profiles in rotation..." picks which profiles are cycled through (all but Default by default).

*: You can change all settings at any time and they will be saved, per window index when you click "Update" or "Save and Apply" in the Window Layout GUI.

### Hotkeys

File > "Hotkeys..." shows all the hotkeys. Click one and press the new key combination (`Esc` cancels), right click clears it. A key combination already used by another hotkey is cleared from that one. Changes apply and are saved right away; Undo (or `Ctrl-Z`) goes back, up to how the hotkeys were when the window opened. If another application already uses some hotkeys, OMB opens that window with them in red so you can pick different ones.

<p align="center">
<img src="sshotHotkeys.png" alt="OMB Hotkeys window">
</p>

### Settings

Your settings are saved in `OpenMultiBoxingSettings.tcl` (and `OpenMultiBoxingSettings<profile>.tcl` for profiles) in same folder as OpenMultiBoxing and can be edited pressing the "Edit Settings" button, then "Reload Settings". That opens the editor Windows uses to edit `.tcl` files (usually Notepad); hotkeys are the `hk,...` entries.

Make sure to also explore the File, Option etc menus (menu bar is at the top of the window) and read mouse over tooltips present in most UI elements of OMB.

<p align="center">
<img src="sshot7_0.png" alt="OMB 7.0 Screenshot">
</p>

Use the clipboard copy/paster in file menu (and check the Options menu to having always open) to **broadcast** text to all your windows.

## Mouse control

You can change the focus following mouse and auto raise/set foreground and the delay

Note that to change the delay you need to hit the Return key

There is a "Track Mouse" (and stop tracking) button (and hotkey, default `Ctrl-Shift-Alt-M`, changed from before for consistency with broadcast as Ctrl-Shift-R) to track coordinates to help doing pixel perfect placement of your windows

You can toggle the focus follow mouse behavior using a hotkey (default `Ctrl-Shift-F`)

You can turn on Left and Right Mouse Click **broadcasting** using the checkbox or the hotkey (default `Ctrl-Shift-M`). Pressing both mouse buttons (ie movement), or leaving any button held for more than half a second (ie camera changes) or having W key held will prevent click broadcasting.

## Other Games

Use Game > "Add game window title..." to add your game's window title; the dialog shows which windows currently match. Use `*` to match any text, e.g. `Game version:*` matches both `Game version:1.2.3` and `Game version:1.2.4`.

Use the Game menu to select your Game and/or check the Capture using foreground window:

<p align="center">
<img src="https://wowopenbox.org/sshot_game_menu.PNG" alt="Game Menu screenshot">
</p>

Read the help text mouse over tooltip:

<p align="center">
<img src="https://wowopenbox.org/sshot_capturefg.png" alt="Capture foreground screenshot">
</p>

You must click your game window and use the capture hotkey (`Ctrl-Shift-C` by default, changeable in settings) to use that mode; after which your game name should be recorded in the Game menu and you can stick to normal Auto Capture (Options Menu).

## Multiple PCs support (network keys/mouse broadcasting)

Select "Listen for other OMB connections" in the options menu on the main computer. Select "Connect to..." in the File menu on the other computers, type the main computer's name. On the main computer, accept the connection request from the other computers.

From then on, mouse or keyboard broadcasting from main will be cloned and repeated on all the connected other PCs.

There is also an option in the Options menu ("Mouse broadcast: remote track movement") to carry mouse movement to other PCs.

The bottom of the main window shows the network status: on the main computer, the number of connected remote PCs; on a remote PC, a "Pause input from ..." checkbox while connected to the main one (to temporarily ignore what it sends).

How a remote PC applies what it receives depends on its captured windows:
- No captured window: full screen mode, keys go to the system (focused window) and mouse moves/clicks are scaled to the primary monitor.
- One window (not skipped): keys, mouse clicks and movement go to that window.
- Several windows: keys and mouse clicks are repeated in each (not skipped) window; mouse movement is ignored as the mouse can't be in several places at once.

## Need more help? Report a problem? Suggest a new feature?

Make sure you are running the latest [release](https://github.com/OpenMultiBoxing/OpenMultiBoxing/releases)

Check if your [issue](https://github.com/OpenMultiBoxing/OpenMultiBoxing/issues/) or suggestion has already been report and if not make a new detailed one

Check the [FAQ](https://github.com/WowOpenBox/WowOpenBox/wiki/FAQ)

Reach out on <a href="https://discord.gg/SMGvEeb"><img src="https://wowopenbox.org/discord.svg" alt="Discord" align="center" height="24pt"></a>
