Ubuntu fresh install on HP Omen/HP gaming Laptops.


**Problem 1: Laptop has  nvidia graphics card and PC freezes while the installation.**

**Problem 2: The system is running in low-graphics mode.**


1. F9 to change boot priority and F10 to change boot settings. (OR find curresponding keys, if your laptop is not HP).
1. Make a bootable USB using either Startup Disk Creator or unetbootin.
1. One error might be efi/boot/mmx64.efi not found. In this case make USB live using unetbootin and copy the file boot efi/boot/grub64.efi in the same folder as before. Unetbootin allows editing live USB, Startup disk creator doesn't.
Nvidia drivers are not compatible with default Ubuntu drivers, so Ubuntu might freeze after installing. Then [reference](https://askubuntu.com/questions/1057659/freeze-installing-ubuntu-18-04-on-omen-by-hp):
    1. Go to grub menu (by pressing shift after bootup)
    1. Go to Grub Ubuntu option (BUT DONT PRESS ENTER) Press e Find the line that starts with: *linux* then add: **modprobe.blacklist=nouveau** after: quiet splash. It should work now.
    1. After working installing follow [[this]](https://linuxconfig.org/how-to-disable-nouveau-nvidia-driver-on-ubuntu-18-04-bionic-beaver-linux) to make it a permanent change. 
1. After installing Nvidia drivers, **reboot** the PC. 
1. If there are any errors regarding after successful installation which might be related to display, like signature not signed with a trusted key nvidia follow steps 4 after b. Remove the display manager name after *quiet flash* and add **modprobe.blacklist=nouveau**.
1. Low graphics mode: Please go [[here]](https://askubuntu.com/questions/141606/how-to-fix-the-system-is-running-in-low-graphics-mode-error) → Might have to re-install nvidia-current.
1. If the graphics problem persists after this: go to step 4 (b).
