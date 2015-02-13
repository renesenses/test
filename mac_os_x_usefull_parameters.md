## Mac OS X usefull parameters
### Delete Yosemite installation push requests

''sudo defaults write /System/Library/LaunchAgents/com.apple.notificationcenterui KeepAlive -bool false
### Show hidden files
''defaults write com.apple.finder AppleShowAllFiles YES
**Alias show hidden files
''alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES; killall Finder /System/Library/CoreServices/Finder.app'
**Alias hide hidden files
''alias hideFiles='defaults write com.apple.finder AppleShowAllFiles NO; killall Finder /System/Library/CoreServices/Finder.app'
