# Custom Mac configurations

I use the following settings and commands to customise my Mac to my needs.

## Preserve order of spaces

System Preferences > Mission Control > uncheck "Automatically rearrange Spaces"

## Use three fingers to drag on trackpad

System Preferences > Accessibility > Pointer Control > Mouse & Trackpad > Trackpad Options > check "Enable dragging" and set to "Three Finger Drag"

## Turn off sound effect for plugging in power adapter

I want my Mac to always be quit when in the library. Therefore I turn off the sound that usually plays when the power adapter is plugged in.

1. `defaults write com.apple.PowerChime ChimeOnNoHardware -bool true`
2. `killall PowerChime`

## Add spacers to Dock

1. `defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'`
2. `killall Dock`

## Always display hidden files in Finder

1. `defaults write com.apple.finder AppleShowAllFiles true`
2. `killall Finder`

## Custom dark mode

I prefer using the dark mode only for specific parts which can be configured as follows.

### Dark menu bar and spotlight search without overall dark mode

1. `defaults write -g NSRequiresAquaSystemAppearance -bool true`
2. Logout and login
3. Set theme in settings to dark

### Enable dark mode for a specific application again (Visual Studio Code as an example)

1. `APP_ID=$(osascript -e 'id of app "Visual Studio Code"')`
2. `defaults write $APP_ID NSRequiresAquaSystemAppearance -bool false`
3. Restart the application
