# Ubuntu24-TweakInstall
- Installer Script Status: Beta
- Tweaker Script Status: Alpha
- Project Status: requires further, testing and development. 

### Description:
Having not used Linux outside of Wsl for a while, there were some basic things I wanted to be more user-friendly. This project then became 2 tools, one for install and one for tweaking, specifically while attempting to install Ubuntu 23.x. Ubuntu Ubuntu 24 that provides, batch and modular, setup options, including basic requirements (batch), emulation libraries (individual), CPU setup (modular), and GPU setup (modular). It ensures system updates and installations are logged and handles errors gracefully. The second script focuses on implementing Windows-like features for Ubuntu 24, including security tweaks that significantly reduce system security and the addition of Windows-like commands. It is designed for controlled environments where reduced security is acceptable. First thing I noticed after going through the processes of the Installer, is that the sound was working on my Usb SoundCard (Note, GPUs Specific Sound Output Install/Setup is, complicated and not specifically implimented). 

### Features:
- Basic OS installation includes system updates and essential tools like vim, nano, curl, wget, git, and htop. (Installer)
- Intermediate OS setup installs development tools, QEMU, libvirt, GCC, GNOME tweaks, and Vulkan drivers. (Installer)
- CPU setup offers options for AMD and Intel CPU-specific tools and optimizations. (Installer)
- GPU setup provides options for AMDGPU (Non-ROCm and ROCm), NVIDIA, and Intel GPU drivers and optimizations. (Installer)
- The main menu dynamically updates with the status of each installation step. (Both)
- Option to implement Windows-like commands such as dir, copy, move, del, md, rd, cls, type, where, echo, shutdown, and restart. (Tweaker)
- Option for disable sudo password prompts, AppArmor, and password complexity requirements to mimic Windows Disable, `UAC` and `Software Protection`, type actions. (Tweaker)
- Windows-like features include adding basic Windows-like commands to the terminal, `cd..`, `dir`, etc. (Tweaker)

### Preview:
- The `Main Menu` for the `Installer`...
```
================================================================================
    Ubuntu-PostInstall-Setup - Main Menu
================================================================================


1. Install Basic Operating System Tools and Utilities

2. Setup Optional Extras for Virtualization and Packages

3. Configure CPU-Specific Optimization and Drivers

4. Configure GPU-Specific Optimization and Drivers


================================================================================
Selection = 1-4, Exit Program = X: 

```
- The `Main Menu` for the `Tweaker` (hopefully it can un-do now too)...
```
================================================================================
    Ubuntu24-Windows-like Features - Main Menu
================================================================================

    1. Disable sudo password prompt (SUDO_NOPASSWD)          (Status: Enabled)

    2. Disable AppArmor (APPARMOR)                           (Status: Enabled)

    3. Disable UFW (Uncomplicated Firewall) (UFW)            (Status: Enabled)

    4. Enable auto-login (AUTO_LOGIN)                        (Status: Disabled)

    5. Implement Windows-like commands (WINDOWS_COMMANDS)    (Status: Enabled)

================================================================================
Selection = 1-5, Exit Program = X:               

```
- The example option execution output, in this case `Basic OS Install`...
```
================================================================================
    Ubuntu24-TweakInstall - Basic OS Install
================================================================================
Get:1 http://archive.ubuntu.com/ubuntu oracular InRelease [126 kB]
Hit:2 http://security.ubuntu.com/ubuntu oracular-security InRelease            
Hit:3 https://ppa.launchpadcontent.net/graphics-drivers/ppa/ubuntu oracular InRelease
Hit:4 http://archive.ubuntu.com/ubuntu oracular-updates InRelease
Hit:5 http://archive.ubuntu.com/ubuntu oracular-backports InRelease
Get:6 http://archive.ubuntu.com/ubuntu oracular/main amd64 Packages [1,438 kB]
Get:7 http://archive.ubuntu.com/ubuntu oracular/main amd64 c-n-f Metadata [31.2 kB]
...

...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in a
uto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdi
ff) in auto mode
Setting up git (1:2.45.2-1ubuntu1) ...
Processing triggers for hicolor-icon-theme (0.18-1) ...
Processing triggers for gnome-menus (3.36.0-1.1ubuntu3) ...
Processing triggers for man-db (2.12.1-3) ...
Processing triggers for desktop-file-utils (0.27-2build1) ...
Basic Tool Installation completed successfully.
Basic OS installation completed.
Press Enter to continue...
```

### INSTRUCTIONS:
1) download and copy file `Ubuntu24-TweakInstall.sh` to a suitable directory.
2) As required, then make the file executable with the  `chmod +x Ubuntu24-TweakInstall.sh`, then run either, `sudo ./Ubuntu24-Installer.sh` or `sudo ./Ubuntu24-Tweaker.sh`.
3) Investigate the appropriate menus, take a look at what it offers, plan what features you intend to use, and select them (ensuring to note errors that pop up).
4) Restart computer, to enable all tweaks/installs to take effect. 
5) If there are issues with anything immediately, then check the notes you made (if any), and investigate appropriately to complete relating install/tweak.
5) Move on to next stage, whatever you determine to be of interest, probal, App Center/Software Manager; At this point any new issues are your own doing.

### Notation:
- Minimum Windows 10 for Vertio/Kvm/QEmu Drivers from `Virtio-Win-0.1.262.Iso`, Windows 7-81 did not complete Setup.  
- For `Ubuntu 22.04` Assistance `https://chatgpt.com/g/g-sQSBQqeR8-sysadmin-for-ubuntu-22-04` and for `Ubuntu 24` assistance go here `https://chatgpt.com/g/g-OPkIvf0HN-java-21-postgresql-16`, I would like to make my own ones but, as usual with gpt sessions, ask for commands to be able to produce output, in relevance to updates you wish to implement, so that then after being fed ouput.
- Its for 24, because thats the version I was using at the time, this may later expand like 22-24 or there will be new version ie Ubuntu26-TweakInstall. 
- `Intermediate OS Setup` includes things like, `KVM` for Machine Emulation and `LLM` things for Model Interference, if you dont need these things, then dont use the option.
- `Start + e` :- Go to `Settings>Keyboard>Add Custom`, then type in `nautilus` for the command, and put `Start + e` in the Shortcut, and give it a fitting title like `Explorer Shortcut`. 
- Its a continuation of the `Fedora40-TweakInstall` project, `Ubuntu24-TweakInstall` is more safer/complete. `Fedora40-TweakInstall` is hidden due to untested tweaks, that require inspection/fixing/testing, which wont happen unless I reinstall Fedora.
- Windows Commands in the terminal are (dont expect them to all work perfect, fixing/improving is done here `/etc/profile.d/windows_commands.sh`)...
```
`dir` - Lists directory contents in a detailed format.
`copy` - Copies files and directories.
`move` - Moves files and directories.
`del` - Deletes files and directories.
`md` - Creates directories.
`rd` - Removes directories.
`cls` - Clears the terminal screen.
`type` - Displays the contents of a file.
`where` - Locates the binary, source, or manual page files for a command.
`echo` - Prints text to the terminal.
`shutdown` - Shuts down the system.
`restart` - Restarts the system.
```

### Development 
Required updates I have noticed from use...
- The, prompts and menus, need to be conformed towards my current standards of format found in other recent programs.
- The windows commands do not include `copy`. Possibly install of them introduces screen garbage in the title...
```
================================================================================
-e \n    Ubuntu24-Windows-like Features - Main Menu
================================================================================
```
- The Individual `VM` related install seems odd now, needs to be made into Modular submenu again. `LLM` option had to be removed, error with build-tools was it? But still, LLM was a bad choice, because people will want custom Torch version possibly. Maybe Just expand out the options for the VM setup, so as to include different VM modules.

### Warnings:
- Installer = Safer, some issues with sound fixing, definately issues with versions.
- Tweaker = Experimental (use at own risk). Alike the Installer, you are NOT intended to just use ALL of the features in the tweaker, be selective, and additionally after you are done, I would keep the tweaker open, and ensure you can still run for example `Firefox`, just to make sure new complex processes can still run, and then if they dont, then you will be able to un-do the relating tweaks, and try again. Again the "Tweaker" script is extremely experimental, so I advise first trying them out on a VM of the OS you intend to use them on.
- If there is some issue with a device, after restarting, after using the Installer, then try re-starting again, this fixed itself for me, but I had a blank screen on one of the monitors, its an iffy old monitor prone to issues though.
