4d-plugin-kiosk
===============

4D plugin to help 4D run as kiosk software by inhibiting certain user actions.

### Platform

| carbon | cocoa | win32 | win64 |
|:------:|:-----:|:---------:|:---------:|
|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|

### Version

<img src="https://cloud.githubusercontent.com/assets/1725068/18940649/21945000-8645-11e6-86ed-4a0f800e5a73.png" width="32" height="32" /> <img src="https://cloud.githubusercontent.com/assets/1725068/18940648/2192ddba-8645-11e6-864d-6d5692d55717.png" width="32" height="32" />

## Syntax

```
mode:=KIOSK Get mode
KIOSK SET MODE (mode)
```

Parameter|Type|Description
------------|------------|----
mode|INT32|``KIOSK_ON`` (``1``) or ``KIOSK_OFF`` (``0``)

## About

This plugin allow 4D to run as a pseudo [kiosk](http://en.wikipedia.org/wiki/Kiosk_software) software.

**Note**: The objective here is to inhibit certain user operations that might terminate the application or move it to the background. It is your responsibility to resize and locate your windows should you wish to completely hide the Desktop (e.g. run full screen).

On Mac:

[SetSystemUIMode](https://developer.apple.com/library/mac/#documentation/Carbon/Reference/Dock_Manager/Reference/reference.html) or [NSApplicationPresentationOptions](https://developer.apple.com/reference/appkit/nsapplicationpresentationoptions?language=objc) is used to

* Hide all system UI elements (including the menu bar and **Dock**).
* Disable the ``cmd``+``tab`` and ``cmd``+``shift``+``tab`` key sequences to switch active processes.
* Disable the ``cmd``+``option``+``escape`` key sequence and the **Force Quit** menu item.
* Disable the **Power** key (if present) and the **Restart**, **Shut Down**, and **Log Out** menu items in the Apple menu.
* Disable the **Hide** menu item in the Application menu.

On Windows:

* Key combination to flip 3D (``Windows``+``Tab``, ``Windows``+``Shift``+``Tab``) is disabled.
* Key combination for flip (``Alt``+``Tab``, ``Alt``+``Shift``+``Tab``) is disabled.
* Key combination to switch application (``Alt``+``Esc``, ``Alt``+``Shift``+``Esc``) is disabled.
* Key combination to display Task Manager (``Ctrl``+``Shift``+``Esc``) is disabled.
* Key combination to quit application (``Alt``+``F4``) is disabled.
* Start Menu key combination (``Windows``, ``Ctrl``+``Esc``) is disabled.
* The Task Tray is hidden.
* The MDI window title bar is hidden.

**Note**: Hot Keys (such as ``Ctrl``+``Alt``+``Delete``) are NOT disabled.
