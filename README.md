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

## [Composer](https://getcomposer.org/)
`curl -sS https://getcomposer.org/installer | php` 

`sudo mv composer.phar /usr/local/bin/composer`

### Composer package: [PHP Standards Recommendations](http://www.php-fig.org/psr/)

`composer global require "squizlabs/php_codesniffer=*"`

### Composer package: [WordPress Coding Standards](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/)
`composer global require wp-coding-standards/wpcs:dev-master`
Let `phpcs` know about the new standards by running:
`phpcs --config-set installed_paths ~/.composer/vendor/wp-coding-standards/wpcs`
