# macOS Setup (Mojave)

A collection of configuration steps (so I don't forget them) for my macOS development environment.

## System Preferences

In **Apple Icon > System Preferences:**

- **Mouse** -> Uncheck Scroll direction: Natural
- **Security & Privacy** -> FileVault: Turn On
- **Security & Privacy** -> Firewall: Turn On

In **Finder**:

- General:
  - Show these items on the desktop: *Hard disks*
  - Change *New finder window show* to open in your *Home Directory*
- Sidebar -> Add *Home*
- Advanced -> *Show all filename extensions*

## Xcode

For installing Xcode command line tools run:

```bash
xcode-select --install
```

## Homebrew

### Installation

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Once installation is complete, run the following command to make sure everything works:

```bash
brew doctor
```

## Git

## iTerm2

### Installation

```bash
brew cask install iterm2
```

## zsh & dotfiles

## Applications

## Python
