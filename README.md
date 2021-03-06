# Pulseaudio-ctl
Simple bash script to allow for control of pulseaudio without alsautils. Simply map the following to keyboard shortcuts in your DE or WM. Xfce4 allows for this under Settings > Keyboard > Application Shortcuts.

	/usr/bin/pulseaudio-ctl mute        ==>  Toggle status of mute
	/usr/bin/pulseaudio-ctl mute-input  ==>  Toggle status of mute for mic
	/usr/bin/pulseaudio-ctl up          ==>  Increase vol by 5 %
	/usr/bin/pulseaudio-ctl down        ==>  Decrease vol by 5 %
	/usr/bin/pulseaudio-ctl set 40      ==>  Set vol to 40%
	/usr/bin/pulseaudio-ctl atmost 30   ==>  Set vol to 30% if current higher than that

## Note
Works with pulseaudio version 5 but not with version 4.

## Configuration
A config file resides in ~/.config/pulseaudio-ctl/config and allows for some options including:

Example:
```bash
# The default setting is for pulseaudio-ctl to NOT increase to volume level
# above 100 % but Some users may wish exceed this level. If this describes
# your use case, uncomment the UPPER_THRESHOLD variable below setting it to
# the new upper threshold.
#
UPPER_THRESHOLD=150

# Push output through libnotify. Set to any value to enable this feature
# and note that you must have /usr/bin/notify-send to use this. On Arch
# libnotify provides this. Other distros may not name it as such.
NOTIFY=yes
```

If config file isn't present script uses default value 100 for the UPPER_THRESHOLD and notifications are disabled by default.

## Links
AUR package: https://aur.archlinux.org/packages/pulseaudio-ctl
