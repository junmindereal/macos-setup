# macOS setup

## Commands
Install Xcode
```bash
xcode-select --install
```

### Install Homebrew
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Update Homebrew
```bash
brew update
```

### Install 1Password
```
brew install --cask 1password
```
Login to 1Password to get all credentials

### Install Iterm 2
```bash
brew install --cask iterm2
```
### Download Gruvbox theme for Iterm [Here](https://github.com/herrbischoff/iterm2-gruvbox)
- In Preferences > Profiles > Colors
  - In lower right corner of the window, Click `Color Presets...`
  - Select `Import`
- Go to Text
  - Change Font to `Menlo`, Regular, Size `16`
- Go to Keys
  - In `Presets...` Select `Natural Text Editing`
- Go to General
  - In Working Directory Select `Reuse previous session's directory`

### Install Bash
```bash
brew install bash
```
### Change shell
Add updated bash to `shells` directory
```bash
echo /usr/local/bin/bash | sudo tee -a /etc/shells
```

Select updated bash
```bash
chsh -s /usr/local/bin/bash
```

### Remove computer name and add current directory with Git branch in Terminal
```bash
mkdir .bash_profile
vim .bash_profile
```
Add these lines of code inside `.bash_profile`
```bash
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```
In above PS1 we defined following properties
- `\w\[\033[33m\]` - current working directory and its displaying color
- `\$(parse_git_branch)\[\033[00m\]` - git branch name and its displaying color

### Remove last login information
```bash
mkdir .hushlogin
```

### Install Git
```bash
brew install git
```

