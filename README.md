# Mizner's new macOS setup

# Download 1password Manually (brew caused issues in the past)

* Install Brew `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

# Disable photos from opening when iPhone is plugged in
`defaults -currentHost write com.apple.ImageCapture disableHotPlug -bool true`

# Brew
* Install Brew `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Brew Packages
```
brew install \
awscli \
composer \
doctl \
neovim \
php@7.4 \
php@8.1 \
wp-cli 
```
### Switching PHP Versions
``
brew unlink php && brew link php@7.4 --force --overwrite
```

### Configure awscli
`aws configure`
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

### awscli sync example
`aws s3 sync . s3://gpipis-test-bucket/aws_sync_example/`

### Connect doctl
https://docs.digitalocean.com/reference/doctl/how-to/install/
`doctl auth init --context <NAME>`

## Brew Cask
```
brew install --cask \
brave-browser \
cleanmymac \
cleanshot \
daisydisk \
dropbox \
google-chrome \
handbrake \
local \
mullvadvpn \
nova \
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

# Node (NVM)
* Install Node Version Manager - https://github.com/nvm-sh/nvm
* `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | zsh`
* `nvm install 16 && nvm install 14`
* Set Default`nvm alias default 14`
* Check Node`node -v`

## App Store
* Paprika
* Be Focused
* Clean Text

## Other Apps
* Paste App (legacy download)

## Zsh
* Set up zsh profile `touch ~/.zshrc`

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
* Kill the Dock (kinda) `defaults write com.apple.Dock autohide-delay -float 2 && killall Dock`

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
