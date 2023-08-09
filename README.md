# wsl2-systemd-alwayson-script
This script allows Linux distributions to run unabated in a Windows user session without an active Terminal. This is especially useful for running [Klipper](https://github.com/Klipper3d/klipper) from a Windows OS.

## Tested On
* Windows 10 (22H2 - 19045)
* Windows Subsystem for Linux (WSL) 2
* Debian (Bookworm)
* KIAUH*: Klipper (v0.11.0)
* KIAUH: Moonraker (v0.8.0)
* KIAUH: Mainsail (v2.6.2)
  
  *Installed through [Klipper Installation And Update Helper (KIAUH)](https://github.com/th33xitus/kiauh)

## Pre-Installation Instructions
This process is intended to be peformed after installing Klipper, Moonraker, and Mainsail. Remember, to use Klipper in WSL2, you must enable systemd by adding the **/etc/wsl.conf** file to your Linux distribution with the following system declaration:  
```sh
[boot]
systemd=true
```

### Run the script and commands
```sh
git clone https://github.com/DamionGans/ubuntu-wsl2-systemd-script.git
cd ubuntu-wsl2-systemd-script/
bash ubuntu-wsl2-systemd-script.sh
# Enter your password and wait until the script has finished
```
### Then restart the Ubuntu shell and try running systemctl
```sh
systemctl

```
If you don't get an error and see a list of units, the script worked.

Have fun using systemd on your Ubuntu WSL2 image. You may use and change and distribute this script in whatever way you'd like. 
I am not responsible for broken installations, tears, or loss of social status when using this script.
