# Coding environment setup
  This walkthrough will show you how to set up your coding environment for coding HTML with VS Code. We will also set up your github global variables to make sure you're ready to push files to Git. Since this is mostly a set-and-forget operation, we've bundled the two of them together into this handy guide.

<br>

## 1. Make sure that Bash is your default shell application...
  Open the terminal and enter...
  ```Bash
  chsh -s /bin/bash
  ```
  You may see the output 'no changes made' - that's fine, that just means you already had BASH as your default shell. Now close the terminal and reopen it. You should now be working in Bash, which is what the content in this course will assume.

<br>

## 1.1. Extra steps for Windows users only...
  **a) Enable copying and pasting hotkeys**
  <br>
  Right-click on the bar at the top of the terminal window and go to ```Properties```. Then check ```Use Ctrl+Shift+C/V as Copy/Paste```.

  **b) Set up an alias for your browser** 
  <br>
  This will make it possible to quickly open files you're working on (e.g., .html pages) in your default browser. Enter the following commands into your terminal shell:
  ```
  export BROWSER='/mnt/c/Windows/explorer.exe'
  ```
  ```
  echo "alias see='explorer.exe'" >> ~/.bashrc
  ```
  ```
  source ~/.bash_profile
  ``` 
  You should now be able to open .html files by entering ```see myfile.html``` in the terminal. This is the equivalent of the convenient ```open myfile.html``` command that Mac users automatically have access to.

  **c) Make sure you have installed the [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) extension for VS Code**
  <br>
  If you followed [the WSL installation instructions I posted on discord](https://oliver-coderacademy.github.io/wsl_setup.html), you'll have this already.

<br>


## 2. Set up PAT's on github...
  * Nagivate to github in your web browser and log in.
  * Click your profile in the top right, and select settings from the dropdown.
  * From the menu tab on the left, select ```Developer Settings```
  * From the menu tab on the left, select ```Personal Access Tokens```
  * Click ```Generate Personal Access Token```
  * Click ```Generate New Token```
  * Enter a simple name - 'my token' is fine
  * Select the ```repo``` checkbox to allow you to push/pull repos from command line
  * Scroll to the bottom and select ```Generate Token```
  * Copy the PAT you generate, and keep that window open just in case! 

<br>

## 3. Save your PAT...
  If you have a password storage app like LastPass, that's the best place to store your PAT. But if you don't, you can save it as an environment variable as follows:
  * In the terminal, take ownership of your bash profile on this machine by entering the following line of code, replacing 'your_user_name' with the username that is displayed in the shell prompt:
  
  ```Bash
  sudo chown your_user_name ~/.bash_profile
  ```

  * In the terminal, add your github PAT to your bash profile environment variables by entering the following line of code, replacing 'your_token_here' with the token you just copied from the github page:
  
  ```Bash
  echo "export GITHUB_PAT=your_token_here" >> ~/.bash_profile && source ~/.bash_profile

  ```

<br>

## 4. Create a directory for all your coursework, and a subdirectory to contain today's exercise...
  ```Bash
  mkdir ccc_coursework
  cd ccc_coursework
  mkdir html_intro
  ```

<br>

## 5. Initialise a git repo in today's subdirectory...
  ```Bash
  cd html_intro
  git init
  ```

<br>

## 6. Set up the credential manager on your machine to authenticate you with GitHub automatically... 
  This one is different for Windows, Mac, and Linux users. 
  
  * My advice for Linux users who want to use a credential manager with Git is to use Libsecret. I don't have a tutorial for you here, but it's pretty easy to get Libsecret up and running, and then tell Git to use it as the default credential manager using similar commands to what follows for Mac and Windows users. Until you set that up, you can skip this step - you'll just be prompted to enter your PAT every time you push.
  * On WSL, enter the following command into the Bash Shell:
  ```Bash 
  git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
  ```
  * On Mac, the command to enter is here:
  ```Bash
  git config --global credential.helper osxkeychain
  ```

<br>

## 7. Make sure you have set your global git configuration...
  * You need to set your name and email so that github knows who you're trying to authenticate as.  We've covered the commands before:
  ```Bash
  git config --global user.name your_username_here
  git config --global user.email your_email_here
  ```


  
