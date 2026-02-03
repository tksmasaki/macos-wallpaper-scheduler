# macos-wallpaper-scheduler

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

ln -sf "$(pwd)"/bin/set_wallpaper_to_morning ~/bin/set_wallpaper_to_morning
ln -sf "$(pwd)"/bin/set_wallpaper_to_day ~/bin/set_wallpaper_to_day
ln -sf "$(pwd)"/bin/set_wallpaper_to_evening ~/bin/set_wallpaper_to_evening
ln -sf "$(pwd)"/bin/set_wallpaper_to_night ~/bin/set_wallpaper_to_night

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
set_wallpaper_to_morning
# set wallpaper to day
set_wallpaper_to_day
# set wallpaper to evening
set_wallpaper_to_evening
# set wallpaper to night
set_wallpaper_to_night
```
