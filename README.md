# Mizner's new macOS setup

* Get 1Password Setup - The One.
* Install Initial Programs
 - Dropbox
 - Dash



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
