# macOS Essential Applications & Settings



## Install essential package manager & turn off analytics

#### This action needs to typing password manually
  
```
# Install homebrew & Xcode Command Line Tools
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


# Turn off analytics
brew analytics off

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
zen \
localsend \
minecraft \
obsidian \
openvpn-connect \
protonvpn \
transmission \
cursor \
chatgpt \
vlc \
vorssaint \
caskhub \
yubico-authenticator \
lulu \
tor-browser \
grandperspective
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


### Proton Authenticator

```
https://apps.apple.com/es/app/proton-authenticator/id6741758667?platform=mac
```



## System Settings

```
# Set a shorter Delay until key repeat		
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 2

# Use plain text mode for new TextEdit documents
defaults write com.apple.TextEdit RichText -int 0

# Check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# Show Path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true

# Show Status bar in Finder
defaults write com.apple.finder ShowStatusBar -bool true

# Avoid creating .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Restart System UI Service
killall SystemUIServer
```


## Others


#### Configure Betterfox

```
https://github.com/yokoffing/BetterFox
```


#### Configure Starship prompt

```
cat >> ~/.zshrc <<'EOF'

# Initialize Starship prompt
eval "$(starship init zsh)"
EOF
```


## CapsLockNoDelay

```
hidutil property --set '{"CapsLockDelayOverride":0}'
```


#### Apple SF and NY fonts

```
https://developer.apple.com/fonts/
```
