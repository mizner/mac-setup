# Mizner's new macOS setup

* Get 1Password Setup - The One.
* Install Initial Programs
 - Dropbox
 - Dash
 - iTerm2
 - VS Code
 - PHPStorm

* Install homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`




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


* Install composer `curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer`
https://progblog.io/How-to-Globally-install-Composer-on-OS-X/
 * WPCS `global require wp-coding-standards/wpcs:dev-master`
