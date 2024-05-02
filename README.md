## My Macbook Pro configuration repo

This repo contains all information about apps/tools/config that I have in my current personal and work laptops. Eveything that cannot be installed or added as an almost automatic reference will be specified on every section.

<!-- START doctoc -->

<!-- END doctoc -->

#### My Computer
I use an Apple M1 Pro Macbook Pro 14 inches laptop with 16GB RAM and 500GB SSD with external SSD drives to store data.

#### SO settings

These are my preferred settings for `Desktop`, `Dock`, `Finder`, and `Preview App` with external installations.

- `System Preferences -> Desktop & Dock`
	- `Dock`
		- Size 25% - Magnification 75%
		- Position on screen -> `Bottom`
		- Minimize windows using -> `Genie Effect`
		- Double-click a window's title bar to -> `Zoom`
		- Minimize windows into application icon -> ✅
		- Automatically hide and show the Dock -> ❌
		- Animate opening applications -> ✅
		- Show indicators for open applications -> ✅
		- Show suggested and recent apps in Dock -> ❌
	- `Desktop & State Manager`
		- Show items -> `On Desktop`
		- Click wallpaper to reveal desktop -> `Always`
		- State Manager -> ❌
		- Show recent apps in State Manager -> ❌
		- Show windows from an application -> `All at Once`
	- `Widgets`
		- Show Widgets -> `On Desktop ✅` -- `In State Manager ✅`
		- Widget style -> `Monochrome`
		- Use iPhone widgets -> ✅
		- Default web browser -> `Openin.app`
	- `Windows`
		- Prefer tabs when opening documents -> `In Full Screen`
		- Ask to keep changes when closing documents -> ❌
		- Close windows when quitting an aplication -> ✅
	- `Mission Control`
		- Automatically rearrange Spaces based on most recent use -> ✅
		- When switching to an application, switch to a Space with open windows for the application -> ❌
		- Group windows by application -> ❌
		- Displays have separate Spaces -> ✅
	- `Hot Corners`
		- RT - `Command key + mouse -> Lock Screen`
		- RB - `Command key + mouse -> Desktop`
- `FINDER -> Settings`
	- `Advanced`
		- ✅ Show all filename extensions
		- ✅ Show warning before changing an extension
		- ✅ Show warning before removing from iCloud Drive
		- ✅ Show warning before emptying the Trash
		- ✅ Remove items from the Trash after 30 days
		- Keep folders on top:
			- ❌ In windows when sorting by name
			- ❌ On Desktop
		- When performing a search:
			- `Search the Current Folder`
	- `Sidebar`
		- ❌ Recents
		- ✅ AirDrop
		- ✅ Applications
		- ✅ Downloads
		- ❌ On My Mac
		- ❌ Movies
		- ❌ Music
		- ❌ Pictures
		- ✅ roganoalien (main user)
		- ✅ iCloud Drive
		- ✅ Shared
		- ✅ Desktop
		- ✅ Documents
		- ✅ MacBook Pro
		- ✅ Hard disks
		- ✅ External disks
		- ✅ CDs, DVDs, and iOS Devices
		- ✅ Cloud Storage
		- ✅ Bonjour computers
		- ✅ Connected servers
		- ❌ Recent Tags
	- `Tags`
		-ed all
	- `General`
		- Show these items on the desktop:
			- ❌ Hard disks
			- ❌ External disks
			- ❌ CDs, DVDs, and iPods
			- ❌ Connected servers
		- New finder windows show:
			- `roganoalien` [folder]
		- ✅ Open folders in tabs instead of new windows
- `Finder -> View -> View Options`
	- ❌ Always open in list view
	- Group by -> `None`
	- Sort by -> `Name`
	- Icon size -> `Las one checked`
	- Text size -> `13`
	- Show columns:
		- ✅ Data Modified
		- ✅ Size
		- ✅ Kind
		- ✅ Use relative dates
		- ✅ Show icon preview
- `Finder -> View -> Show Preview Options`
	- ✅ Tags
	- ✅ Dates
		- ✅ Created
		- ✅ Modified
		- ✅ Last opened
	- ✅ Show Quick Actions

#### Appearance

`Auto` instead of having only light or dark mode and `multicolor` as accent and highlight color

#### Keyboard

- `Key repeat rate`
	- 7
- `Delay until repeat`
	- 4
- Adjust keyboard brightness in low light -> ✅
- Turn keyboard backlight off after inactivity -> `After 5 seconds`
- Press [World icon] key to -> `Change Input Source`
- Keyboard navigation -> ❌
- `Keyboard Shortcuts`
	- `Input Sources`
		- ✅ Select next source in input menu -> `Ctrl + Option + Command + Space`
	- `Screenshots`
		- Disable everything (for CleanShot App)
	- `Spotlight`
		- Disable everything (for Alfred App)
- `Input Sources`
	- Add
		- ABC
		- Latin American

## Homebrew

[Homebrew](https://brew.sh/) allows us to install tools and apps from the command line.

To install it, open up the built in `Terminal` app and run this command:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, we will use it (via Alfred) to install everything else we need.

### Install formulae and casks from brew

### Manual casks and formulaes

#### Mangal
Manga reader from terminal

`brew tap metafates/mangal`

`brew install mangal`

### Alfred Homebrew Plugin

Install the [Alfred Homebrew Plugin](https://github.com/fniephaus/alfred-homebrew/releases) so we can easily install formulae and casks directly from Alfred.