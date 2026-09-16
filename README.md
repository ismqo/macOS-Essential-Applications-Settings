# macOS Essential Applications & Settings



Here is my macOS auto install script.

⚠️⚠️⚠️ 

Base on personal experience, author isn't responsible for any data lost or damage, proceed at your own risk.

⚠️⚠️⚠️


## Install essential package manager & turn off analytics

#### This action needs to typing password manually
  
```
# Install homebrew & Xcode Command Line Tools
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


# Turn off analytics
brew analytics off

```


## Install Rosetta 2 via Command Line on Apple Silicon Mac

#### This action needs to typing password manually
  
```
# Skip the license agreement by providing an additional flag
/usr/sbin/softwareupdate --install-rosetta --agree-to-license

```


## Install CLI Applications

```
brew install \
git \
lazygit \
mas \
node@20 \
opencode \
pnpm \
starship \
yt-dlp 
```



## Install GUI Applications without password

```
brew install --cask \
anydesk \
google-chrome \
eqmac \
ghostty \
helium-browser \
localsend \
minecraft \
obsidian \
openvpn-connect \
protonvpn \
transmission \
visual-studio-code \
vlc \
vorssaint \
cask-hub
```


## Install MAS Applications

#### Sign into the Mac App Store GUI app manually First!

```
mas install 1352778147
```

My Favorite Applications

| APP_ID    | Name      |
| :-------- | :-------- |
|1352778147 |Bitwarden  |



## System Settings

```
# Set a shorter Delay until key repeat		
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 2

# Disable window animations ("new window" scale effect)
defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool false

# Use plain text mode for new TextEdit documents
defaults write com.apple.TextEdit RichText -int 0

# Expand save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true

# Check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# Show Path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true

# Show Status bar in Finder
defaults write com.apple.finder ShowStatusBar -bool true

# Show icons for hard drives, servers, and removable media on the desktop
defaults write com.apple.finder.plist ShowExternalHardDrivesOnDesktop 1 && \
defaults write com.apple.finder.plist ShowHardDrivesOnDesktop 1 && \
defaults write com.apple.finder.plist ShowMountedServersOnDesktop 1 && \
defaults write com.apple.finder.plist ShowRemovableMediaOnDesktop 1

# Hide tags in Finder sidebar
defaults write com.apple.finder.plist ShowRecentTags 0

# Avoid creating .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# Enable the Develop menu and the Web Inspector in Safari
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true && \
defaults write com.apple.Safari IncludeDevelopMenu -bool true && \
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true && \
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true && \
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Show absolute path in finder's title bar
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

# Show build duration for Xcode
defaults write com.apple.dt.Xcode ShowBuildOperationDuration YES

# Show system icon in Apple title bar
defaults write com.apple.systemuiserver menuExtras -array \
"/System/Library/CoreServices/Menu Extras/Bluetooth.menu" \
"/System/Library/CoreServices/Menu Extras/Clock.menu" \
"/System/Library/CoreServices/Menu Extras/AirPort.menu" \
"/System/Library/CoreServices/Menu Extras/Battery.menu" \
"/System/Library/CoreServices/Menu Extras/TimeMachine.menu" \
"/System/Library/CoreServices/Menu Extras/Displays.menu" \
"/System/Library/CoreServices/Menu Extras/VPN.menu" \
"/System/Library/CoreServices/Menu Extras/User.menu" \
"/System/Library/CoreServices/Menu Extras/WWAN.menu" \
"/System/Library/CoreServices/Menu Extras/Volume.menu"

# Restart System UI Service
killall SystemUIServer
```


## Others


#### Configure Starship prompt

```
cat >> ~/.zshrc <<'EOF'

# Initialize Starship prompt
eval "$(starship init zsh)"
EOF
```

#### Configure Ghostty

```
mkdir -p ~/.config/ghostty
cat > ~/.config/ghostty/config << 'EOF'
# Typography
font-family = Hack Nerd Font
font-size = 13
font-thicken = true
adjust-cell-height = 1

# Window & Appearance
window-padding-x = 8
window-padding-y = 8
background-opacity = 0.5
background-blur=macos-glass-regular
theme= Xcode Dark

# Behavior
mouse-hide-while-typing = true
cursor-style = block
cursor-style-blink = false
scrollback-limit = 100000

# Clipboard
clipboard-read = allow
clipboard-write = allow
EOF
```



#### Install Fonts

```
brew install --cask font-hack-nerd-font
```


## CapsLockNoDelay

```
hidutil property --set '{"CapsLockDelayOverride":0}'
```

