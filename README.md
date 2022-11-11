# LDRS-Onboarding

# Computer Setup

## Get Access for 
1. Github Repo
2. Railway Application
3. Slack
4. Trello

## Install WSL
1. Run Ubuntu Application on windows to setup your UNIX account (If it does not run by default on computer restart)<br>
2. Create username and password for your ubunutu root user. This is different then the windows login or LDRS login.

## In windows File explorer add to quick access 
Path : \\wsl$\Ubuntu\home\user

## Install Terminal Application
1.Install Windows Terminal from [microsoft store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-ca&gl=ca)
2. Add Ubuntu as the default terminal window
   - Press the down arrow at the top of the terminal. ("\/")
   - Settings
   - Change Default Profile to Ubuntu
   - Hit Save and close and reopen windows terminal

## Make sure WSL is on version 2

- In command Prompt (user)
- run `Wsl -l -v`
- If running WSL 1 update to WSL 2

## Install Text Editor
The default text editor is VSCode. If you want to use something else let me know.

## Extensions for VsCode
1. Instal WSL Extension from Microsoft
2. Install GitHub Repositories Extension from Microsoft
3. Install Remote Repositories Extension from Microsoft
4. Github Pull Requests and Issues
5. Gitlens - Git supercharged

### Frontend Extensions
1. Prettier
2. ES Lint
3. Prettier ES Lint
4. ES7 +React/Redux/React-Native snippets

### Backend Extensions
1. Python
2. Django

# Installing in Terminal

## Update Linux Kernel
`sudo apt-get update && sudo apt-get upgrade -y` 

## Install git if it is not installed
`sudo apt install git`

## Check it installed correctly
`git --version`

## Install [Github CLI](https://github.com/cli/cli)
`type -p curl >/dev/null || sudo apt install curl -y
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y`

## Login to Github through CLI
1. `gh auth login`
2. Select Github.com
3. Select HTTPS
4. Select 'Y'
5. Select Login with Web Browser
6. Copy One Time Code
7. Press Enter
8. Paste Code in Browser
9. Authorize Github
10. Upon return to terminal you should see a confirmation that you are logged in.

## Cache Remote Login Credentials. Remove placeholders and run individually
1. `git config --global user.name "Enter Full Name"`
2. `git config --global user.email "Enter Email"`
3. `git config --global credential.helper cache --timeout=3600`

## Install [NVM](https://github.com/nvm-sh/nvm)
1. `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash`
2. `nvm install --lts`

## Test if it installed correctly
1. `node -v'
2. `npm -v`

## Check if python is installed
1. `python3 --version`
2. If not `sudo apt install python3`

# Install Pipenv. We will use it to manage our python packages.
`sudo apt install pipenv -y`

# Optional Terminal Improvements

## [Install Oh My Zsh (Optional Terminal Upgrade)](https://github.com/ohmyzsh/ohmyzsh)
1. `sudo apt install zsh -y` - 
2. `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

## Customize Zsh (Optional)
`code ~/.zshrc`

### Change in the config file the theme
ZSH_THEME="random" to try out random themes until you find one you like

### I personally use
ZSH_THEME="xiong-chiamiov-plus"

### Add nvm to zsh
**Important - Not Optional if using zsh** <br>
plugins=(git nvm)

### Access WSL Files on Windows
In windows File explorer add to quick access to be able to access wsl files on windows.
Path : \\wsl$\Ubuntu\home\user

### Change the path in the terminal 
`code ~/.bashrc`

### Change in the config file 
At the bottom of the file add
export PS1=

and chose how you want to display the path. Only add one line.

### Some examples:
- export PS1="\w$ " # full working dir
- export PS1="\W$ " # basename of working dir
- export PS1="\u@\W $ " # username @ working dir
- export PS1="[\t] \u@\h:\w\$ " # timestamp + username + host + working dir

- \w full working directory
- \W basename of the current working directory
- \h hostname
- \u username
- \t time 24-hour HH:MM:SS
- \T time 12-hour HH:MM:SS
- \@ time 12-hour am/pm

### I personally use
export PS1="[\t] \u@\W $ " #timestamp + username @ working dir

Save the setting and close the terminal and open a new instance.

# Setting up the Repo in WSL
1. Open the terminal
2. mkdir LDRS
3. cd LDRS
4. `gh repo clone ldrsInvestmentsAdmin/EAOS' To clone repo locally
5. cd EAOS
6. `code .` to open vsCode in the folder
