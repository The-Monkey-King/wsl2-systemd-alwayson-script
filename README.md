# wsl2-systemd-alwayson-script
This script allows Linux distributions to run unabated in a Windows user session without an active Terminal. This is especially useful for running [Klipper](https://github.com/Klipper3d/klipper) from a Windows OS.

## Tested On
* Windows 10 (22H2 - 19045)
* Windows Terminal 1.17.11461.0
* Windows Subsystem for Linux (WSL) 2
* Debian (Bookworm)
* KIAUH*: Klipper (v0.11.0)
* KIAUH: Moonraker (v0.8.0)
* KIAUH: Mainsail (v2.6.2)
  
  *Installed through [Klipper Installation And Update Helper (KIAUH)](https://github.com/th33xitus/kiauh)

## Installation Instructions
This process is intended to be peformed after installing Klipper, Moonraker, and Mainsail. Remember, to use Klipper in WSL2, you must enable systemd by adding the **/etc/wsl.conf** file to your Linux distribution with the following system declaration:  
```sh
[boot]
systemd=true
```

### Open Terminal and Linux Instance Tabs
This example Linux distribution does not need an Administration level account. Just right-click on the Windows CMD icon and select Terminal. Once the application opens, click on the downward caret and select your Linux instance. You will need both tabs open for the next set of instructions.

![Terminal shell](https://github.com/The-Monkey-King/wsl2-systemd-alwayson-script/assets/8395267/0fe5c97b-86ec-4651-88df-99af475a3478)


### Linux Tab: Run this script and these commands

```sh
git clone https://github.com/The-Monkey-King/wsl2-systemd-alwayson-script.git
cd wsl2-systemd-alwayson-script/
bash wsl2-systemd-alwayson-script.sh
# Enter your password and wait until the script has finished
```

### Terminal Tab: Run these commands
```sh
setx WSLENV BASH_ENV/u
setx BASH_ENV /etc/bash.bashrc
```

### Restart and Test
1. Close the Linux tab
2. In the Terminal tab, run the command:
```sh
wslconfig /t <Linux_instance>
```
3. Restart Linux by opening it in a new tab
4. In the Linux tab, run the command:
   ```sh
   systemctl
   ``` 
If you see a list of units and no errors, the script worked.
You can test this further by opening a web browser to your Mainsail page (usually localhost / 127.0.0.1). Close the Terminal application. Klipper should still work as expected.

This script is Open Source and free to implement under GNU General Public License v3.0.
I am not responsible for broken installations, tears, or loss of social status when using this script.
