# Mizner's new macOS setup

* add global NPM packages to finder nav
* Finder Preferences
  * Show all filename extenstions
* Show hidden files 
  * `defaults write com.apple.finder AppleShowAllFiles YES`
  * Relaunch Finder
* Disable SIP (System Integrity Protection)
  * Restart, hold CMD + R for recovery mode
  * Run `csrutil disable`
