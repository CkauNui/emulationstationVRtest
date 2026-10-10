# VR mouse mode (laser pointer / thumbstick-as-wheel)

This build of EmulationStation adds two optional settings for VR streamers
(Virtual Desktop, Steam Link, Air Link...) that show the desktop and emulate a mouse.
Both are OFF by default, so nothing changes unless you enable them.

Add these two lines to `es_settings.cfg` (in the `.emulationstation` folder of your Retrobat),
with ES closed:

```xml
<int name="MouseWheelStepMs" value="180" />
<bool name="MouseSelectOnly" value="true" />
```

- `MouseWheelStepMs` (default 0 = off): every wheel event becomes a single step, accepted at most
  once per N milliseconds. 150-200 is a good start. Lower = faster scrolling.
- `MouseSelectOnly` (default false): a left click only selects a game, it never launches it.
  Launch with Enter (the A button if your streamer maps it so); right click stays "back".

To go back to stock behaviour, remove the two lines (or set 0 / false).
