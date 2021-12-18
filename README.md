# Mizner's new macOS setup

* Get 1Password Setup

# Disable photos from opening when iPhone is plugged in
`defaults -currentHost write com.apple.ImageCapture disableHotPlug -bool true`

## Install Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Brew
* Install homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
* Fix permissions for brew: `sudo chown -R $(whoami) /usr/local`

# Node
* Install NVM - https://github.com/nvm-sh/nvm: `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.36.0/install.sh | bash`
```
brew install \
composer \
doctl \
fzf \
wp-cli \
yarn \
```

```
brew cask install \
1password \
alfred \
cleanmymac \
cleanshot \
daisydisk \
discord \
dropbox \
google-chrome \
handbrake \
local \
mullvadvpn \
notable \
postman \
rectangle \
slack \
tableplus \
telegram \
transmit \
tor-browser \
tower \
visual-studio-code \
vlc \
zoom \
```

## App Store
* Paprika
* Be Focused
* Clean Text

## Other Apps
* Paste

## Finder
* View > Show View Options
	* Sort by Date Added
* Preferences
	* General
		* New Finder = Downloads
	* Advanced
		* Show all filename extensions
		* Search the current folder


* add global NPM packages to finder nav
* Finder Preferences
  - Show all filename extenstions

## Dock
* Kill the Dock (kinda) `defaults write com.apple.Dock autohide-delay -float 5 && killall Dock`

## SIP
* Disable SIP (System Integrity Protection)
  - Restart, hold CMD + R for recovery mode
  - Run `csrutil disable`

## [Composer](https://getcomposer.org/)
`brew install composer`

`sudo mv composer.phar /usr/local/bin/composer`

### Composer package: [PSR (PHP Standards Recommendations)](http://www.php-fig.org/psr/)

`composer global require "squizlabs/php_codesniffer=*"`

### Composer package: [WordPress Coding Standards](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/)
https://kellenmace.com/set-up-php-codesniffer-in-phpstorm-with-wordpress-coding-standards/
https://tommcfarlin.com/php-codesniffer-with-composer/

`composer global require wp-coding-standards/wpcs:dev-master`

### Update .zshrc
Add `PATH=$PATH:~/.composer/vendor/bin` to your `.zshrc` file (usually directly in your home directory)

Let `phpcs` know about the new standards by running:
`phpcs --config-set installed_paths ~/.composer/vendor/wp-coding-standards/wpcs`

### Install sshpass
https://gist.github.com/arunoda/7790979
`brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb`

### Download jq (Bash Variables from JSON)
https://stedolan.github.io/jq/download/
`brew install jq`

## Speed Up Mac Animations
http://osxdaily.com/2015/01/06/make-the-window-resizing-animation-speed-instant-in-mac-os-x/
`defaults write -g NSWindowResizeTime -float 0.003`

## Install tmux
https://github.com/tmux/tmux/wiki
`brew install tmux`

## Mac Screenshots (swap to jpg)
`defaults write com.apple.screencapture type jpg;killall SystemUIServer`


## Time Machine Exclusions
https://gist.github.com/PyYoshi/2d6d1eadf745e3fc5274c7b0a8b00983
* Node modules: `find `pwd` -type d -maxdepth 3 -name node_modules | xargs -n1 sudo tmutil addexclusion -p`


## VS Code
    "telemetry.enableTelemetry": false
