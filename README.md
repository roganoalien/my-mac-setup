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

In the repo there are two files:

- `brew-cask.txt` -- a list of brew cask packages
- `brew-formulae.txt` -- a list of brew formulaes

They're split in order to work and avoid errors about not finding some packages.

To install them you need to run `brew install $(cat brew-formulae.txt)` but you need to be inside the current repo folder. And do the exact same for the `brew-cask.txt` file with a little differnce: 

`brew install --cask $(cat brew-cask.txt)`

In case it all fails then we will try the same installation with: 

`xargs brew install > brew-cask.txt` && `xargs brew install > brew-formulae.txt`

#### Install Nerd Fonts

In order to install automatically all the nerdfonts available in Github you should run the following commands in your terminal: 

```shell
brew tap homebrew/cask-fonts

brew search '/font-.*-nerd-font/' | awk '{ print $1 }' | xargs -I{} brew install --cask {} || true
```

The first command adds the repo to the list of formulae that homebrew tracks. And the last one searchs for every formulae that has `font-` and `-nerd-font` in the name, prints them and use them as argument, then installs them as a `--cask` and the last part that says true is to avoid breaking the installation if some font fails installation in the process.

### Manual casks and formulaes

#### Mangal
Manga reader from terminal

```shell
brew tap metafates/mangal

brew install mangal
```

#### Other apps that needs to be manually installed

##### Charmstone

App that uses a key shortcut to open a menu from the mouse position that you can add shortcuts to specific apps: 

- [Charmstone](https://charmstone.app/) -- Needs a license that I already have

##### Postgres

App to run postgres DB server [GUI APP]

- [Postgres](https://www.postgresql.org/)

##### Powertab Editor

- [Power Tab Editor](https://powertab.github.io/)

##### Appstore apps 

- Color Picker [System Color Picker]
- Gapplin [SVG preview]
- Pure Paste [Paste without format]
- Infuse [Video Player]
- Contrast [Contrast Evaluation from colors]
- Logic Pro
- Lottie Files [Lottie Animations Viewer]
- Encrypto
- Colorslurp
- The Unarchiver
- Shazam
- Logitech app for mouses

##### Setapp Apps 

Setapp is a subscription based appstore that lets you install every app from their store without paying extra. These are the apps that I've used: 

- CleanMyMac X (Clean garbage and temp files, uninstall apps, etc)
- Time Out (Pomodoro app)
- CleanShot X (Take better screenshots)
- Pareto Security (Checks for security stuff in your mac and lets you know whats wrong and how to fix it)
- Rocket Typist (Snippets through keyboard shortcut)
- Openin (Default browser to make everylink to ask in which browser would you like to open the link in)
- In Your Face (fullscreen meetings notification to prevent skiping them or not seeing them)
- Craft (Note taking app)
- TablePlus (DB GUI visualizer and config)
- Lungo (Keep your mac awake)
- PDF Squeezer (Compress PDFs)
- Paletro (Access app menu commands through a keyboard shortcut)
- Batteries (display battery level of all your devices connected via bluetooth)
- DevUtils (Dev various utils)
- Dropzone (download and connect to server and other utils)

## Alfred

[Alfred](https://www.alfredapp.com/) is a great app that replaces Spotlight. Although there are multiple ways to install it. In this repo it has already been handled by brew with the casks. `Warning`: it needs the powerpack in order to work correctly.

All the config for Alfred is in [my own repository](https://github.com/roganoalien/alfred4-config)

### Alfred Homebrew Plugin

Install the [Alfred Homebrew Plugin](https://github.com/fniephaus/alfred-homebrew/releases) so we can easily install formulae and casks directly from Alfred.

## Visual Studio Code

Configuration for my VSCode app.

##### Extensions installed

```md
aaron-bond.better-comments
amazonwebservices.amazon-q-vscode
amazonwebservices.aws-toolkit-vscode
amazonwebservices.codewhisperer-for-command-line-companion
attilabuti.vscode-mjml
beardedbear.beardedicons
bierner.jsdoc-markdown-highlighting
biomejs.biome
bitbelt.converttoasciiart
blanu.vscode-styled-jsx
bradgashler.htmltagwrap
bradlc.vscode-tailwindcss
chakrounanas.turbo-console-log
christian-kohler.npm-intellisense
christian-kohler.path-intellisense
csstools.postcss
dbaeumer.vscode-eslint
denoland.vscode-deno
dotenv.dotenv-vscode
editorconfig.editorconfig
enkia.tokyo-night
esbenp.prettier-vscode
evondev.indent-rainbow-palettes
file-icons.file-icons
golang.go
graphql.vscode-graphql
graphql.vscode-graphql-execution
graphql.vscode-graphql-syntax
jerryhong.autofilename
keyring.lua
kisstkondoros.vscode-gutter-preview
logerfo.procfile-support
meezilla.json
mgmcdermott.vscode-language-babel
mhutchie.git-graph
ms-azuretools.vscode-docker
ms-python.debugpy
ms-python.isort
ms-python.python
ms-python.vscode-pylance
ms-vscode.cmake-tools
ms-vscode.cpptools
ms-vscode.cpptools-extension-pack
ms-vscode.cpptools-themes
msjsdiag.vscode-react-native
naumovs.color-highlight
oderwat.indent-rainbow
prisma.prisma
quick-lint.quick-lint-js
rafamel.subtle-brackets
snyk-security.snyk-vulnerability-scanner
steoates.autoimport
sumneko.lua
tushortz.python-extended-snippets
unifiedjs.vscode-mdx
usernamehw.errorlens
virgilsisoe.hammerspoon
vunguyentuan.vscode-postcss
waderyan.gitblame
willluke.nextjs
wix.vscode-import-cost
yoavbls.pretty-ts-errors
quicktype.quicktype
```

###### Installation of extensions

The list of extensions need to be inside a `.txt` file and then run the following command

```shell
cat vs-extensions.txt | xargs -L1 code --install-extension
```

###### Uninstall extensions

Do the same but change the last part of shell code

```shell
cat vs-extensions.txt | xargs -L1 code --uninstall-extension
```

##### VSCode biome formatter

Change the following commands to allow biome

```json
	"[javascript]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[javascriptreact]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[json]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"editor.codeActionsOnSave": {
		"quickfix.biome": "always",
		"source.organizeImports.biome": "always"
	},
	"[html]": {
		"editor.defaultFormatter": "biomejs.biome",
	},
	"[jsonc]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[typescriptreact]": {
		"editor.defaultFormatter": "vscode.typescript-language-features",
		"editor.defaultFormatter": "biomejs.biome"
	},
```

##### VSCode settings

```json
{
	"workbench.colorCustomizations": {},
	"workbench.iconTheme": "file-icons",
	"files.associations": {
		"*.ejs": "html",
		"html": "html",
		"javascript": "html",
		".env*": "dotenv",
		"*.css": "tailwindcss"
	},
	"editor.colorDecorators": false,
	"editor.cursorWidth": 3,
	"editor.renderWhitespace": "all",
	"javascript.updateImportsOnFileMove.enabled": "always",
	"editor.insertSpaces": false,
	"editor.cursorSurroundingLines": 5,
	"editor.tabCompletion": "on",
	"editor.tabSize": 4,
	"diffEditor.ignoreTrimWhitespace": false,
	"editor.fontLigatures": true,
	"[javascript]": {
		"editor.fontLigatures": "'ss02', 'ss19'"
	},
	"editor.detectIndentation": false,
	"editor.wrappingIndent": "indent",
	"emmet.includeLanguages": {
		"nunjucks": "html",
		"javascript": "javascriptreact",
		"typescript": "typescriptreact"
	},
	"emmet.triggerExpansionOnTab": true,
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": "explicit"
	},
	"editor.fontFamily": "'Fira Code', Menlo, Monaco, 'Courier New', monospace",
	"editor.fontSize": 13,
	"editor.semanticHighlighting.enabled": false,
	"[mjml]": {
		"editor.useTabStops": true,
		"editor.tabSize": 4
	},
	"indentRainbow.errorColor": "rgba(243,123,130,0.1)",
	"indentRainbow.colors": [
		"rgba(3, 4, 94,0.15)",
		"rgba(2, 62, 138,0.15)",
		"rgba(0, 119, 182, 0.15)",
		"rgba(0, 150, 199,0.15)",
		"rgba(0, 180, 216,0.15)",
		"rgba(72, 202, 228,0.15)",
		"rgba(144, 224, 239,0.15)",
		"rgba(144, 224, 239,0.1)",
		"rgba(144, 224, 239,0.05)",
		"rgba(144, 224, 239,0.025)"
	],
	"[plaintext]": {
		"editor.quickSuggestions": {
			"other": false,
			"comments": false,
			"strings": false
		}
	},
	"editor.matchBrackets": "always",
	"editor.suggestSelection": "first",
	"[dart]": {
		"editor.formatOnSave": true,
		"editor.formatOnType": true,
		"editor.rulers": [80],
		"editor.selectionHighlight": false,
		"editor.suggest.snippetsPreventQuickSuggestions": false,
		"editor.suggestSelection": "first",
		"editor.tabCompletion": "onlySnippets",
		"editor.wordBasedSuggestions": "off"
	},
	"security.workspace.trust.untrustedFiles": "open",
	"[typescriptreact]": {
		"editor.defaultFormatter": "vscode.typescript-language-features"
	},
	"editor.bracketPairColorization.enabled": true,
	"editor.guides.bracketPairs": "active",
	"editor.cursorBlinking": "expand",
	"[prisma]": {
		"editor.defaultFormatter": "Prisma.prisma"
	},
	"terminal.integrated.env.osx": {
		"FIG_NEW_SESSION": "1",
		"CW_NEW_SESSION": "1",
		"Q_NEW_SESSION": "1"
	},
	"editor.accessibilitySupport": "off",
	"editor.formatOnPaste": true,
	"workbench.list.smoothScrolling": true,
	"workbench.statusBar.visible": true,
	"workbench.sideBar.location": "right",
	"workbench.editor.showTabs": "none",
	"telemetry.telemetryLevel": "off",
	"autoimport.showNotifications": true,
	"git.autofetch": true,
	"terminal.integrated.fontFamily": "MesloLGL Nerd Font Mono",
	"editor.tokenColorCustomizations": {
		"[*Light*]": {
			"textMateRules": [
				{
					"scope": "ref.matchtext",
					"settings": {
						"foreground": "#000"
					}
				}
			]
		},
		"[*Dark*]": {
			"textMateRules": [
				{
					"scope": "ref.matchtext",
					"settings": {
						"foreground": "#fff"
					}
				}
			]
		},
		"textMateRules": []
	},
	"editor.formatOnSave": true,
	"dotenv.enableAutocloaking": false,
	"tailwindCSS.experimental.classRegex": [
		["clsx\\(([^)]*)\\)", "(?:'|\"|`)([^']*)(?:'|\"|`)"]
	],
	"tailwindCSS.files.exclude": [
		"**/.git/**",
		"**/node_modules/**",
		"**/.hg/**",
		"**/.svn/**",
		"**/.json/**",
		"**/.d.ts/**"
	],
	"tailwindCSS.showPixelEquivalents": true,
	"tailwindCSS.hovers": true,
	"subtleBrackets.disableNative": false,
	"subtleBrackets.style": {
		"borderWidth": "2px",
		"borderStyle": "none none solid none"
	},
	"github.copilot.enable": {
		"*": true,
		"plaintext": false,
		"markdown": false,
		"scminput": false
	},
	"editor.stickyScroll.enabled": true,
	"typescript.updateImportsOnFileMove.enabled": "always",
	"biome_lsp.trace.server": "verbose",
	"biome.lspBin": "",
	"workbench.colorTheme": "Tokyo Night",
	"window.zoomLevel": 1,
	"editor.defaultFormatter": "biomejs.biome",
	"[tailwindcss]": {
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"editor.cursorSmoothCaretAnimation": "on",
	"editor.snippetSuggestions": "top",
	"editor.linkedEditing": true,
	"git.openRepositoryInParentFolders": "never"
}
```