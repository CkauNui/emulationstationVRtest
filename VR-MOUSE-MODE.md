# VR mouse mode (laser pointer / thumbstick-as-wheel)

This build of EmulationStation adds two optional settings for VR streamers
(Virtual Desktop, Steam Link, Air Link...) that show the desktop and emulate a mouse
(trigger/A = left click, B = right click, thumbstick = wheel).
Both are OFF by default, so nothing changes unless you enable them.

Add these two lines to `es_settings.cfg` (in the `.emulationstation` folder of your Retrobat),
with ES closed:

```xml
<int name="MouseWheelStepMs" value="180" />
<bool name="MouseSelectOnly" value="true" />
```

- `MouseWheelStepMs` (default 0 = off): every wheel event becomes a single step, accepted at most
  once per N milliseconds. 150-200 is a good start. Lower = faster scrolling.
- `MouseSelectOnly` (default false): VR mode for the game list.
  - A left click on a game only **selects** it, it never launches it.
  - The bottom help bar is reduced to **OPTIONS, MENU, BACK and LAUNCH** (all clickable).
    LAUNCH replaces "GAME OPTIONS (HOLD)" and starts the selected game.
  - A click on the themed top area (video / fanart / description), which normally opens
    "Game Options", **launches the game** instead.
  - Game Options are still reachable by holding a click on a game in the list.
  - Right click stays "back".
  - On the system carousel the help bar shows only SELECT and NAVIGATION BAR
    (SEARCH/RANDOM, RANDOM and CHOOSE are hidden).
    A left click anywhere outside the system carousel (artwork / video / description area)
    enters the selected system, same as SELECT.

To go back to stock behaviour, remove the two lines (or set 0 / false).
