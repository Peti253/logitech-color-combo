# logitech-color-combo
A script which allows you to easily display all matching key combinations on your RGB keyboard.

## Compatible Keyboards
The script ist currently using [g810-led](https://github.com/MatMoul/g810-led) to control the LEDs of following Keyboards:
- G213 Prodigy
- G410 Atlas Spectrum
- G413 Carbon
- G512 Carbon
- G513 Carbon
- G610 Orion Brown
- G610 Orion Red
- G810 Orion Spectrum
- G815 LIGHTSYNC
- G910 Orion Spark
- G910 Orion Spectrum
- GPRO

## Install on Linux

Just download the [ColorCoding.py](https://gitlab.com/p3t1/logitech-color-combo/-/blob/main/ColorCoding.py) (if you want you can download an [example config](https://gitlab.com/p3t1/logitech-color-combo/-/blob/main/Keyboard.yaml) too), and save it anywhere you like.

After you created a config file (if you haven't downloaded the example one), you can add a key to turn the script on and off:
##### on KDE plasma
Go to the settings. Go to "Workspace" > "Shortcuts". In "Custom Shortcus", create a new shortcut, and instert

`/usr/bin/python3 /[path]/ColorCoding.py /[path]/Keyboard.yaml`

under "Action". If you're not using Keyboard.yaml as config, make shure to change it to the name of your config file.
##### on GNOME
Go to the settings. Go to "Keyboard" > "Customize Shortcuts" > "Own Shortcuts" and click on "Add Shortcut". Insert

`/usr/bin/python3 /[path]/ColorCoding.py /[path]/Keyboard.yaml`

as command.

## Configure

The config consists of classes that can be imported from each other and contain both the color data of the keys and the shortcuts. Please make shure you have a class called `[standard]`, which the script will use, if you havent configuered specific shortcuts or key colours for the currently active window.

inside the classes you can use following commands (key an group names are imported from g810-led):

| Command | Funtcion | Example | Explanation |
| ------ | ------ | ------ | ------ |
| i | Import | i standard | imports everything from standard to the current class |
| k | set key colour | k g ff0000 | sets the colour of the G-key to red |
| a | set the colour of all keys | a ffffff | sets all keys to white |
| g | set key-group colour | g modifiers 0000ff| sets all modifiers to blue |
| c | shortcut with ctrl | c v 00ff00  | sets the colour of V to green if ctrl is pressed |
| m | shortcut with meta | m e ffff00 | sets the colour of E to yellow if meta is pressed |
| x | shortcut with alt | x f4 ff0000| sets the colour of the F4-Key to red if alt is pressed |
| s | shortcut with shift | s a 0000ff | sets the colour of a to blue if shift is pressed |
| b | block | b s | blocks the shift key, so nothing changes, if only the shift key is pressed |

You can combine **c**, **m**, **x** and **s** to make bigger shortcuts, for example `cx t 00ff00` would make the T-Key green if both ctrl **and** alt are pressed
