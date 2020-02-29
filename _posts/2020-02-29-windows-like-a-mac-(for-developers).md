---
layout: post
title:  "Windows Like a Mac (for developers)"
date:   2020-02-29 09:00:00 +0200
categories: tech
image:  2020-02-29-windows-like-a-mac-(for-developers).png
comments: true
---
In my experience, Macs are great but expensive, Hackintosh too much work and Linux lacks Adobe's Creative Suite. That's why I present you with this guide to make Windows work more like a Mac.

## The Launcher
If you like the Cmd + Space launcher in Mac you want to try Wox for Windows which does mostly the same things.

1. Download and install from [here](https://github.com/Wox-launcher/Wox/releases) (you may need to scroll down to the "Latest release" to find the files and you'll need to install both "Wox" and "Everything" to make it all work)
2. When running you can change the hotkey to be "Ctrl+Space" by right-clicking the window
3. If you don't like the pixel perfectness of the default dark theme, [here's](a fix for that). (To install it copy the theme to %LOCALAPPDATA%\Wox\app-(your app version)\Themes)
4. That should look something like this:

    ![Wox instead of Spotlight Search on Cmd+Space](/images/2020-02-29-wox.png)

## Keybindings
The biggest difference for the keyboard between Mac and PC is that the Cmd key in Mac does what the Ctrl key in Windows does (and they have switched places too). So the first thing to do is remap them:

1. Download and install this program called [SharpKeys](https://github.com/randyrants/sharpkeys/releases)
2. Then open it up and press "Add" then on the left side you can press "Type Key" and then press your Left Ctrl-key, press enter, and in the right box again press "Type Key" and then press your Left Alt-key. Then do the other way around. In the end you should end up with it looking like this:

    ![Use SharpKeys to remap your Alt-key to behave like a Cmd-key](/images/2020-02-29-sharp-keys.png)

1. Then we need to download and install a program called [Auto Hot Key](https://www.autohotkey.com).
2. Then I have two custom made scripts for you which can be download below
    
    [Alt-F4 to Cmd-Q.ahk](/shared/files/Alt-F4 to Cmd-Q.ahk)
    
    [Alt-Tab Correction.ahk](/shared/files/Alt-Tab Correction.ahk)

3. Save these files wherever you like.
4. Before you run them you can open them in a text editor to see what they do, but the "Alt-Tab Correction" make your alt-tab and alt-tab-shift work as you would expect on a Mac/PC again, and "Alt-F4 to Cmd-Q" makes you being able to quit programs using your Alt-Q keys.
5. To make this work after a reboot, right-click them and choose "Send to > Desktop (create shortcut)".
6. Then, press Win + R and type: "shell:startup" to open up the autostart folder and copy these newly created shortcuts from your desktop to this folder.

## Screenshot replacement
Mac's new screenshot tool is a lot greater than Windows PrintScreen + Paint, Snipping Tool and Snip & Sketch in my opinion. But once I started using Lightshot I could see it was a lot closer, and even better in some use cases. Installing it and changing it's keybindings makes you feel right a lot more convenient in Windows.

1. Download and install Lightshot from [here](https://app.prntscr.com/en/download.html)
2. Once installed you can change Default hotkey to "Ctrl + 4" and Instant save of the fullscreen to "Ctrl + 5" to mimick the Mac behaviour as much as possible.
3. Try your new screenshot tool by pressing Ctrl + 4 and once you edited how you want it you can just copy it with Ctrl + C and you're done.

    ![Lightshot screenshot](/images/2020-02-29-lightshot.png)


## Get a Decent Terminal

### Install a Linux Distribution
One of the big things I've learned to appreciate with Macs is the Unix terminal. Now, you have that alternative for your Windows PC as well. 

1. Press the Windows Button (or click the Windows Flag)
2. Search for PowerShell, right-click the top result, and select "Run as administrator"-option.
3. Run:

    ```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux```
4. You can now install many of the most common Linux distributions which are found in the Windows Store. Here's a link to the [latest LTS version of Ubuntu](https://www.microsoft.com/store/productId/9NBLGGH4MSV6) for instance which we'll use for the rest of this guide.
5. After it's installed you can press "Run" directly from the Windows Store (or press Win + R and write "bash")
6. And when running, make sure to press the Menu title, and press "Properties" and under Options check "Use Ctrl+Shift+C/Ctrl+Shift+V as Copy/Paste"


### Install and Customize Windows Terminal
Now it's time to elevate your Terminal experience.

1. Install a Powerline supported font, in this case, we'll use [DejaVuSansMono for Powerline](/shared/files/DejaVu Sans Mono for Powerline.ttf)
2. Install Microsoft's Windows Terminal through this [link](https://www.microsoft.com/store/productId/9N0DX20HK701).
3. Run the Terminal and open the Settings:

    ![Windows Terminal](/images/2020-02-29-windows-terminal.png)
    
4. Change the following lines:

    From 
    
        "defaultProfile": "{YOUR POWERSHELL GUID}",
    
    To 
    
        "defaultProfile": "{YOUR UBUNTU GUID}",

    From

        {
            "guid": "{YOUR UBUNTU GUID}",
            "hidden": false,
            "name": "Ubuntu",
            "source": "Windows.Terminal.Wsl",
        },

    To

        {
            "guid": "{YOUR UBUNTU GUID}",
            "hidden": false,
            "name": "Ubuntu",
            "source": "Windows.Terminal.Wsl",
            "fontFace" : "DejaVu Sans Mono for Powerline",
            "fontSize" : 10
        },

    From
    
        "keybindings": []
    
    To        

        "keybindings": [
        {
        "command" : "closeTab",
        "keys" : 
        [
            "ctrl+w"
        ]
        },
        {
        "command" : "newTab",
        "keys" : 
        [
            "ctrl+t"
        ]
        }

        ]

5. Quit and restart your Windows Terminal and will now open up using Ubuntu as default.

### Install Oh My Zsh
1. Next level is to install the popular Oh My Zsh plugin to your console. Continue in your Windows Terminal Window instance of Ubuntu and install Zsh by running:

    ```sudo apt install zsh```

2. Install Oh My Zsh by running this command:

    ```wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh```

3. Next, we want zsh to run at login, so run the following command to edit your .bashrc

    ```nano ~/.bashrc```

    Comment out everything by adding # in front of every line that doesn't have it and then add this line at the end:

    ```bash -c zsh```

4. Now reboot your terminal to see that changes. (But don't be alarmed, it's going to look better than this)

5. Next, we're going to install Powerline 9K. Download it by running this:

    ```git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k```

6. Then edit your .zshrc by running:

    ```nano .zshrc```

7. And change this line:

        ZSH_THEME="robbyrussel"

    to this:

        ZSH_THEME="powerlevel9k/powerlevel9k"

8. Now, reboot your terminal and it should look something like this:

    ![Windows Terminal with Oh My Zsh](/images/2020-02-29-windows-terminal-oh-my-zsh-styled.png)




### Set Up Git and SSH keys for Windows and Ubuntu
Now, when we have our shell we need to add our SSH keys so both Windows with supposedly Visual Studio Code and our newly created terminal can use them.

1. We'll start installing Chocolatey (like Homebrew for Mac). Press Win + R and type "Powershell", then right-click it and open with "Run as administrator"

2. Then paste in the following command:

        Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

3. Then run ```refreshenv``` to make the changes happen in that console

4. Then install Git in windows by running ```choco install git```

5. Next up we will generate our SSH keys, and to get that work on Windows 10 we first have to start the ssh-agent manually, we allow that by still being in our elevated PowerShell console and running:

    ```Get-Service -Name ssh-agent | Set-Service -StartupType Manual```

6. Then we can generate a key by running this and following the instructions:

    ```ssh-keygen``` 

7. Now the key exists in our Windows ssh-agent and we can add the public key to our provider.

8. Make also sure to run the following command so you don't run into problems later:

    ```ssh -T git@github.com```

    ```git config --global user.name "[FIRST_NAME] [LAST_NAME]"```

    ```git config --global user.email "[YOUR@EMAIL.COM]"```

9. Now we can use the same ssh-keys for Ubuntu and our new terminal as well, we copy them by running this:

    ```cp -r /mnt/c/Users/[YOUR_USERNAME]/.ssh ~/.ssh```

10. And then change file permissions for the private key:

    ```sudo chmod 600 ~/.ssh/id_rsa```

11. Now we can add these to Ubuntu's SSH agent by running these two commands:

    ```eval `ssh-agent -s` ```

    ```ssh-add ~/.ssh/id_rsa```

12. Then, as one last step we can add the git config here as well (allowed host got copied if you followed this guide completely):

    ```git config --global user.name "[FIRST_NAME] [LAST_NAME]"```

    ```git config --global user.email "[YOUR@EMAIL.COM]"```

## Install Visual Studio Code
Visual Studio Code is a nice editor, especially when using Windows Subsystem for Linux. To make it play nicely with our Powerline 9K theme we need to add our font to our VS Code settings.

1. If you don't have it already download and install it from [here](https://code.visualstudio.com/)

2. Then in "File > Preferences > Settings" search for terminal. Then scroll down to where it says "Terminal > Integrated: Font Family" and in that box type "DejaVu Sans Mono for Powerline" (the font we installed earlier)

3. Then by clicking "View > Terminal" you will see the terminal below the screen. And there next to the plus sign, you can choose WSL if not already selected.

4. Then you're done!

![Visual Studio Code](/images/2020-02-29-wsl-in-vscode.png)

## To conclude...
It's a little bit tricky to get everything working as you want but with a little tweaking Windows can act mostly like your Mac. I hope this helped you making the best out of two worlds.