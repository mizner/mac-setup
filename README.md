# Mizner's new macOS setup

* Get 1Password Setup - The One.
* Install Initial Programs
 - Dropbox
 - Dash
 - iTerm2
 - VS Code
 - PHPStorm

# Brew
* Install homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
* Fix permissions for brew: `sudo chown -R $(whoami) /usr/local`
* `brew install doctl` Digital Ocean CLI tools


* add global NPM packages to finder nav
* Finder Preferences
  - Show all filename extenstions
* Kill the Dock (kinda) `defaults write com.apple.Dock autohide-delay -float 5 && killall Dock`
* Show hidden files 
  - `defaults write com.apple.finder AppleShowAllFiles YES`
  - Relaunch Finder
* Disable SIP (System Integrity Protection)
  - Restart, hold CMD + R for recovery mode
  - Run `csrutil disable`

## [Composer](https://getcomposer.org/)
`curl -sS https://getcomposer.org/installer | php` 

`sudo mv composer.phar /usr/local/bin/composer`

### Composer package: [PSR (PHP Standards Recommendations)](http://www.php-fig.org/psr/)

`composer global require "squizlabs/php_codesniffer=*"`

### Composer package: [WordPress Coding Standards](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/)
https://kellenmace.com/set-up-php-codesniffer-in-phpstorm-with-wordpress-coding-standards/
https://tommcfarlin.com/php-codesniffer-with-composer/

`composer global require wp-coding-standards/wpcs:dev-master`

Let `phpcs` know about the new standards by running:

`phpcs --config-set installed_paths ~/.composer/vendor/wp-coding-standards/wpcs`

### Update .zshrc
Add `PATH=$PATH:~/.composer/vendor/bin` to your `.zshrc` file (usually directly in your home directory)

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
