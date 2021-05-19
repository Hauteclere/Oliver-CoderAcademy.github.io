# Installing WSL 2

Welcome!

This document will guide you through the process of installing Windows Subsystem for Linux 2 for the CoderAcademy CCC course. This guide was put together using Microsoft's official instructions for installing WSL, with some added tweaks from yours truly to make it easier to follow.

Some things to keep in mind before we begin:

* You only need to follow these instructions if you're using a Windows laptop. Mac users are lucky because they already have access to the resources we'll be installing WSL for, and anyway, the W in WSL stands for WINDOWS - there is no MSL!
* It's ok to just follow these instructions by rote, if you don't understand what you're doing. Some of the steps outlined below might make a lot more sense after a few weeks' worth of coursework, and that's fine. Just work through them for now and don't worry if you're feeling lost. All will be made clear. :) If you need help, reach out to the teaching team on Discord!

Happy hacking, and see you in class!

-- Oliver


## Step 0. - Checking Requirements:
First of all let's make sure you have everything you need to install WSL 2.

1. ### Time.
    *This isn't such a big undertaking, but it's better not to be rushed. It would be annoying to get halfway through and get cut off. If your computer is fast and completely up-to-date, and you don't run into any extra complications, these steps could take as little as ten minutes. More likely, you'll need some time for downloads, updates, and processing. Make sure you're not going to run out of batteries on your laptop or be kicked out of a cafe before you can finish.*
1. ### You need to have an active internet connection.
    *These instructions require you to download files from the internet in order to upgrade your computer's functionality. You'll need to have uninterrupted access to an internet connection with decent bandwidth, that will let you download without running up enormous data charges.*
1. ### You need to be running Windows 10 as your operating system.
    *This one is non-negotiable I'm afraid, although for most people it won't be a problem. WSL is only supported in Windows 10, and there's really no good substitute. Trust me when I say that you want to be running Windows 10 anyway - accept no imitators. If you think you'll have trouble getting Windows 10 on your device, contact the teaching team on Discord for help.* :)
1. ### You need to have your OS relatively up to date.
    **You'll need at least version 2004 in order to continue with this walkthrough.**
    *I know it can be annoying to stay on top of Windows updates - sometimes you don't feel like restarting your PC, or you can't spare the bandwidth for downloading the update. But we are studying Cyber Security in this course, and I promise you: nothing compromises your security like an out-of-date OS. I recommend taking the time now to install however many updates you have waiting. It'll make staying up to date in the future easier, and it'll make your PC smile.*
    1. #### Checking what version of Windows 10 you have installed:
        To check your version and build number, press ```Windows Logo Key + R```, type ```winver```, and select ```OK```. A window should pop up with the version and license details of your OS. If it lists a version number lower than 2004, you'll definitely need to update before continuing.  
    1. #### Updating Windows If Necessary
        If you have determined that you need to update your OS, you can download a handy Windows 10 Update Assistant file that will bring you up to the latest version from: 
        ```
        https://www.microsoft.com/software-download/windows10
        ```
        Just click ```Update Now``` to download the installer, and then double click the resulting file to run it. This may take some time.


## Step A. - Enabling the Windows Subsystem for Linux
    
1. Press the ```Windows Logo Key```
1. Type ```powershell```
1. Right click on ```Windows PowerShell``` when it appears in the dropdown and select ```Run as administrator```
1. You may be prompted to allow the program to "make changes to your device".  If so, click ```Yes``` 
1. Type/paste the following command into the resulting PowerShell window, and press ```Enter``` to run it:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
Leave PowerShell open for now!


## Step B. - Enable the Virtual Machine Platform
1. Type/paste the following command into PowerShell and press ```Enter``` to run it:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```


## Step C. - Restart Your Machine
*Even if you only just restarted it to perform a million updates, it needs to restart again to finish installing the features you just turned on. If it wants to update **again**, then let it do it's thing. Can't be too up to date!*


## Step D. Download the Version of the Linux Kernel Update Package That Matches Your System:
1. Open PowerShell the same way you did earlier, type/paste the following code, and press ```Enter``` to run:
```
systeminfo | find "System Type"
```
PowerShell will think for a moment and then display your system-type on the screen.

* If you have an x64-based PC, download the package at:
```
https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
```
* If you have an ARM64-based PC, download from:
```
https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi
```


## Step E. Run the Linux Kernel Update Package
1. Find the file you just downloaded and double-click it to run it. If you are prompted to allow permissions to it, click ```Yes```.


## Step F. Set WSL 2 as your default version of WSL
1. Open PowerShell as before, type/paste the following command, and press ```Enter``` to run:
```
wsl --set-default-version 2
```


## Step G. Download Linux Distribution 20.04 LTS from the microsoft store:
1. Here's a link to the page you want:
```
https://www.microsoft.com/store/apps/9n6svws3rx71
```
1. Click ```Get``` to begin the process of downloading the distro. 
1. If you're not logged into your Microsoft Account for some reason, you'll be prompted to log in now.
1. You may also be prompted to open the Microsoft Store app to continue this process. If so, click ```Yes```, and then click ```Get``` again to begin the download. It may take a little while, depending on your download speed.


## Step H. Download and Install VS Code and the Remote - WSL extension:
1. Here's a link to the page with VS Code:
    ```
    https://code.visualstudio.com/download
    ```
    Download the installer and then double click it to run. Follow the prompts to install.
1. Here's a link the the Remote - WSL extension
    ```
    https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
    ```
    Click ```install```, and you'll be prompted to allow it to open in VS Code. Once you allow it, it should add itself to your VS Code extensions. 



## Step I. Launch WSL 2/Ubuntu for the first time!
***Congratulations.***  *You did it!*
* You can launch WSL 2/Ubuntu by pressing ```Windows Logo Key```, typing ```Ubuntu```, and then clicking the orange logo when it appears.
* The first time you launch, you will be prompted to enter a username and password. Your username should be all lowercase letters or numnbers, with no special characters or spaces (although you can use ```-``` and ```_```). 
* ***Make sure you remember your username and password! :D*** 
* Some tips on managing your Ubuntu distribution can be found here:
    ```https://docs.microsoft.com/en-us/windows/wsl/user-support```
* To code using VS Code in your WSL 2 instance of Ubuntu, just launch Ubuntu, navigate to any directory you please, and type:
```
code .
```

* There's no going back now - you're a hacker. Make sure you attend your classes at CoderAcademy so you can learn to use your powers for good and not evil.