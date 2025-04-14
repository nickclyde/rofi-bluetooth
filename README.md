<div align="center">
<h3>rofi-bluetooth</h3>
<img src="https://github.com/ClydeDroid/rofi-bluetooth/raw/master/.meta/menu.gif">

`bluetoothctl` `rofi` `dmenu`

</div>

## Installation

Install from [AUR (rofi-bluetooth-git)](https://aur.archlinux.org/packages/rofi-bluetooth-git/), or:

1. Install dependencies: [rofi](https://github.com/davatorium/rofi), bluetoothctl (provided by `bluez-utils` in Arch) and [bc](https://archlinux.org/packages/extra/x86_64/bc/)
1. `git clone git@github.com:ClydeDroid/rofi-bluetooth.git`
1. `cd rofi-bluetooth`
1. `./rofi-bluetooth`
1. (Optional) For easy access, add the script somewhere in your `$PATH`.

### Polybar configuration

`NOTE:` In order to properly display the bluetooth icon, you will need to use an iconic font in your bar, e.g. [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts)

```
[module/bluetooth]
type = custom/script
exec = rofi-bluetooth --status
interval = 1
click-left = rofi-bluetooth &
```

### Waybar configuration

```
"bluetooth": {
	// "controller": "controller1", // specify the alias of the controller if there are more than 1 on the system
	"format": " {status}",
	"format-disabled": "", // an empty format will hide the module
	"format-connected": " {num_connections} connected",
	"tooltip-format": "{controller_alias}\t{controller_address}",
	"tooltip-format-connected": "{controller_alias}\t{controller_address}\n\n{device_enumerate}",
	"tooltip-format-enumerate-connected": "{device_alias}\t{device_address}",
	"on-click": "rofi-bluetooth"
},
```

### i3 keybinding

```
bindsym $mod+b exec --no-startup-id rofi-bluetooth
```

### Hyprland keybinding

```
bind = $mainMod, B, exec, rofi-bluetooth
```

### Thanks for the inspiration!

- [firecat53/networkmanager-dmenu](https://github.com/firecat53/networkmanager-dmenu)
- [x70b1's bluetoothctl polybar script](https://github.com/polybar/polybar-scripts/tree/master/polybar-scripts/system-bluetooth-bluetoothctl)
