# mac-wallpaper-setter

Set macOS wallpapers by time of day using LaunchAgents and AppleScript.

## Schedule

- 05:00: Set to Morning wallpaper
- 07:00: Set to Day wallpaper
- 17:00: Set to Evening wallpaper
- 19:00: Set to Night wallpaper

## Requirements

- macOS (verified on macOS Tahoe 26.2)
- Wallpaper images at:
  - `~/Pictures/wallpapers/morning.png`
  - `~/Pictures/wallpapers/day.png`
  - `~/Pictures/wallpapers/evening.png`
  - `~/Pictures/wallpapers/night.png`

## Setup

```shell
# Change directory to mac-wallpaper-setter project root: `cd /path/to/mac-wallpaper-setter`
# If you prefer a different scripts folder path, feel free to change it.
mkdir -p ~/src/scripts
ln -sf "$(pwd)"/scripts/set_wallpaper_to_morning.scpt ~/src/scripts/set_wallpaper_to_morning.scpt
ln -sf "$(pwd)"/scripts/set_wallpaper_to_day.scpt ~/src/scripts/set_wallpaper_to_day.scpt
ln -sf "$(pwd)"/scripts/set_wallpaper_to_evening.scpt ~/src/scripts/set_wallpaper_to_evening.scpt
ln -sf "$(pwd)"/scripts/set_wallpaper_to_night.scpt ~/src/scripts/set_wallpaper_to_night.scpt

ln -sf "$(pwd)"/LaunchAgents/set.wallpaper.to.morning.plist ~/Library/LaunchAgents/set.wallpaper.to.morning.plist
ln -sf "$(pwd)"/LaunchAgents/set.wallpaper.to.day.plist ~/Library/LaunchAgents/set.wallpaper.to.day.plist
ln -sf "$(pwd)"/LaunchAgents/set.wallpaper.to.evening.plist ~/Library/LaunchAgents/set.wallpaper.to.evening.plist
ln -sf "$(pwd)"/LaunchAgents/set.wallpaper.to.night.plist ~/Library/LaunchAgents/set.wallpaper.to.night.plist

ln -sf "$(pwd)"/bin/restart_wallpaper_setter ~/bin/.

# Run the following command to bootstrap the LaunchAgents
restart_wallpaper_setter
```

## Change wallpaper manually

```shell
# set wallpaper to morning
osascript ~/src/scripts/set_wallpaper_to_morning.scpt
# set wallpaper to day
osascript ~/src/scripts/set_wallpaper_to_day.scpt
# set wallpaper to evening
osascript ~/src/scripts/set_wallpaper_to_evening.scpt
# set wallpaper to night
osascript ~/src/scripts/set_wallpaper_to_night.scpt
```
