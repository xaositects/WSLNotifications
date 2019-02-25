# WSLNotifications
A powershell script to give the ability to send notifications to Windows 10 desktop from within WSL. I'm not  PS guru so there are likely many things tha tcould be made better about this script.

It's mainly inspired by this article [raymoncamden.com](https://www.raymondcamden.com/2017/09/25/calling-a-powershell-script-from-wsl) and the lack of the ability to use libnotify-bin in WSL to send messages to the systray in Windows.

Usage:

From within WSL (I'm using Ubuntu 1804 here)

```powershell.exe -NoProfile -ExecutionPolicy Bypass -File "C:\PATH_TO_ALERT\alert.ps1" -msg "this is a message"```


- Make sure the path to the alert file alert.ps1 is the Windows path, not the /mnt/c path.
- Replace "this is a message" with your message. 


I've included a bash script to call this. Make sure to edit the script path in the bash file and chmod the bash script to 700.

I personally like to create a directory called "bin" in my home dir in WSL, and edit .bashrc to include

```export PATH=$PATH:~/bin```

on the last line so you can execute scripts in your bin dir from the CLI.

In this case, you'd execute

```send-message "some message here"```

from within WSL to send a message to the windows notifications.
