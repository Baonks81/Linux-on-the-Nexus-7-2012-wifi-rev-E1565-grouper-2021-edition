# Linux-on-the-Nexus-7-2012-wifi-rev-E1565-grouper-2021-edition
Linux on Nexus 7 2012

I created Ubuntu MATE 20.04.1 LTS and ArchLinux ARMv7 image and kernel 5.15.0-rc4-next-postmarketos-grate and 5.14-rc3-next-grate for Nexus 7 2012 wifi rev. E1565. Following guides:







[URL unfurl="true"]https://forum.xda-developers.com/t/linux-on-the-acer-iconia-tab-a500-2020-edition.4136023/post-83215067[/URL]







[URL unfurl="true"]https://forum.xda-developers.com/t/wip-postmarketos.4025065/[/URL]







What works:



- flashing



- USB (including OTG)



- WiFi



- Bluetooth



- Sound



- LCD + Touchscreen (with rotation)



- light sensor



- NFC (should work, driver loads, initialize, no NFC device to test)







What doesn't work (yet):



- camera



- 3D support (partial working, es2gears/es2tri/glxgears run but glmark2-es2 crashed)







Dev docs:



- https://wiki.postmarketos.org/wiki/The_Mainline_Kernel







Kernel sources:



- used kernel https://github.com/grate-driver/linux/







Sample picture:



5600315_IMG_20210823_085623.jpg







Contributors



okias, digetx, Worlblender, Baonks81



Source Code: https://gitlab.com/postmarketOS/pmbootstrap/







ROM OS Version: Linux



ROM Firmware Required: shipped with ROM



Based On: Linux 5.15.0-rc4-next-20211011-postmarketos-grate and Linux 5.14.0-rc3-next-20210729-grate







Version Information



Status: Testing







Download link: 



Ubuntu MATE 20.04.1 LTS ext4 rootfs kernel 5.15.0-rc4-next-20211011-postmarketos-grate



[URL unfurl="true"]https://drive.google.com/drive/u/0/folders/1xubwe_tmtA7MXtykH42hdcxKgPBoyVJJ[/URL]







Ubuntu MATE 20.04.1 LTS ext4 rootfs kernel 5.14.0-rc3-next-20210729-grate:



https://drive.google.com/drive/folders/1cLs1q5thzrsuHNVM08OaQ3OWASgf6t-R







Ubuntu MATE 21.10 Impish Indri ext4 kernel 5.15.0-rc4-next-20211011-postmarketos-grate:



[URL unfurl="true"]https://drive.google.com/drive/u/1/folders/1Ib3Xdz0oG1EiWU2MDjyr7o6LxN8xHWCt[/URL]







Ubuntu 21.10 Impish Indri pre-installed server ext4 kernel 5.15.0-rc4-next-20211011-postmarketos-grate:



https://drive.google.com/folderview?id=1GC9I_hZl3H6LVd2IG_XYJLHrq6Bj-c6C







ArchLinux ARMv7 kernel 5.15.0-rc4-next-20211011-postmarketos-grate



[URL unfurl="true"]https://drive.google.com/drive/u/0/folders/1dGFlh5SVMsgHulqkVo14hEvPEQ5LiTY8[/URL]







ArchLinux ARMv7 kernel 5.14.0-rc3-next-20210729-grate f2fs: https://drive.google.com/drive/folders/13ja5utmNSyNiz4xKTG5qcoBqRNv9qVYw?usp=sharing







ArchLinux ARMv7 kernel 5.14.0-rc3-next-20210729-grate ext4: https://drive.google.com/drive/folders/1szK5trBse8-j1hSIgzZDppL3R6ySNSCP







More distros here:







F2FS:







[URL unfurl="true"]https://drive.google.com/drive/folders/1VBo6z-xi5riBv9ayqWsktTh6aV-3Wiin[/URL]







[URL unfurl="true"]https://drive.google.com/drive/u/0/folders/1PCpcRpo-I4hACtL_6PWWRh9dKMQ-ui4y[/URL]







Fedora Xfce 35 armhfp ext4 kernel-5.15.0-rc4-next-20211011-postmarketos-grate:



[URL unfurl="true"]https://drive.google.com/drive/u/1/folders/1nB2sIrPsGnpQvEYavGF9i1PB2AUAxvHH[/URL]







Fedora Xfce 34 armhfp ext4 kernel-5.14.0-rc3-next-20210729-grate: https://drive.google.com/drive/folders/1LbffvuU2B2r6ydbaTxvK2KNX_MdLxrrn







openSUSE Leap 15.3 ext4 kernel 5.15.0-rc4-next-20211011-postmarketos-grate



[URL unfurl="true"]https://drive.google.com/drive/u/0/folders/1iaBFiZp1S-fj7GV50AfGyvs8DFAubN4O[/URL]







openSUSE Leap 15.3 ext4 kernel 5.14.0-rc3: https://drive.google.com/drive/folders/19ArXlOwX2xN8-SHjxPMzMQ-kj-Xkvbf0







Debian Bulleye ext4 kernel-5.15.0-rc4-next-20211011-postmarketos-grate



[URL unfurl="true"]https://drive.google.com/drive/u/0/folders/10Vv9-YV9vkd2BB20mn09OjMYYuKgG-L9[/URL]







Debian ext4: https://drive.google.com/drive/folders/1jhq1v5ejOazDB1wSF-ZS0FxBc_QIPUFD







Install guide for Ubuntu MATE 20.04.1 LTS:







Please check your tablet is grouper or tilapia by command







TWRP (adb shell) $ grep androidboot.baseband=unknown /proc/cmdline && echo grouper || echo tilapia







Checking hardware revision of grouper(E1565 or PM269)







TWRP (adb shell) $ find /sys/devices/ | grep -c max776 && echo You have E1565







TWRP (adb shell) $ find /sys/devices/ | grep -c tps6591 && echo You have PM269







Reference link here:



[URL unfurl="true"]https://wiki.postmarketos.org/wiki/Google_Nexus_7_2012_(asus-grouper)[/URL]







1. Unlock bootlader and upgrade stock Android 5.1.1 Build LMY47V



2. Install TWRP 3.3.1-0 or later



3. Connect Nexus 7 to PC/Latop. Go to bootloader and flash boot



    # adb start-server



    # adb reboot bootloader (or press Power button + Volume Down button to come bootloader)



    # fastboot flash boot boot-kernel-5.14-rc3-next-grate.img (rename boot.img-asus-grouper-kernel-5.14-rc3-next-grate)



4. TWRP -> Advance -> Terminal



    # df



    # umount /dev/block/mmcblk0p__  <- fill partition number (2 times)



5. Back PC/Laptop, # unxz -v ubuntu-mate-20.04.1-*.img.xz



    # adb push /path/to/ubuntu-mate-20.04.1-desktop-armhf+asus-grouper-kernel-5.14-rc3-next-grate.img /dev/block/mmcblk0p__  <- fill partition number







grouper has likely data on /dev/block/mmcblk0p9 but make sure!

tilapia has likely data on /dev/block/mmcblk0p10 but make sure!





6. Utilities in /opt folder such as: cpufreq, temp_throttle, clear_ram, kde-auto-rotate



7. Install preload, tlp, bleachbit compton compositor in ubuntu source







Compton:



compton --backend glx --vsync opengl-swc --glx-no-stencil --unredir-if-possible --glx-no-rebind-pixmap --glx-swap-method 3 --paint-on-overlay -b







8. Update sysctl and cpufreq



    # sudo sysctl -p



    # sudo chmod +x /opt/cpufreq.start



    # sudo sh /opt/cpufreq.start



9. Remove rpi packages



    # sudo apt-get remove --purge libraspberrypi-bin libraspberrypi0 linux-firmware-raspi2 linux-headers-raspi linux-image-raspi linux-raspi pi-bluetooth rpi-eeprom u-boot-rpi flash-kernel linux-headers-5.4.0-1015-raspi linux-image-5.4.0-1015-raspi linux-image-5.4.0-1022-raspi linux-modules-5.4.0-1015-raspi linux-modules-5.4.0-1022-raspi linux-raspi-headers-5.4.0-1022 fwupd fwupd-signed gnome-firmware



10. Install grate-driver: https://launchpad.net/~grate-driver/+archive/ubuntu/ppa/+packages?field.name_filter=&field.status_filter=published&field.series_filter=focal



    # sudo add-apt-repository ppa:grate-driver/ppa



11. Update sources.list and upgrade Ubuntu MATE 20.04.3 LTS. Enjoy!







Install chromium without snap:



[URL unfurl="true"]https://askubuntu.com/questions/1204571/chromium-without-snap/1206153#1206153[/URL]







$ sudo nano /etc/apt/sources.list







deb http://deb.debian.org/debian/ bullseye contrib main non-free



# deb http://deb.debian.org/debian-debug/ bullseye-debug contrib main non-free



# deb-src http://deb.debian.org/debian/ bullseye contrib main non-free







deb http://security.debian.org/debian-security bullseye-security main contrib non-free



# deb-src http://security.debian.org/debian-security bullseye-security main contrib non-free







# Backports



deb http://deb.debian.org/debian bullseye-backports main contrib non-free







$ sudo apt update && sudo apt install chromium







Accelerate chromium create



# sudo nano /etc/chromium/local.conf







unset GDK_BACKEND







Insert --use-gel=egl in /usr/share/applications/chromium.desktop at line



Exec=/bin/chromium --use-gl=egl %U







Fix chromium authentication keyring:







$ sudo apt install seahorse







$ seahorse







Create new Password keyring for application with default name was "Default keyring"







Install guide for ArchLinuxARMv7:



The same install Ubuntu MATE 20.04.1 LTS steps







Thanks to:



- grate-driver team



- postmarketOS



- Ubuntu MATE for rpi


Reference link: https://tinhte.vn/thread/ubuntu-mate-20-04-3-lts-cho-nexus-7-2012-wifi-rev-e1565-kernel-5-14-rc3-support-usb-otg.3198632/

It's all creating a .desktop at startup applications



# sudo chmod +x /opt/clear_ram

# sudo chmod +x /opt/cpufreq.start

# sudo chmod +x /opt/temp_throttle



# sudo visudo



ALL ALL=(ALL) NOPASSWD: /opt/clear_ram, /opt/cpufreq.start, /opt/temp_throttle



Menu -> Preferences -> Startup Applications



In foreach command create one .desktop:



1. sudo /opt/clear_ram



2. sudo /opt/cpufreq.start



3. sudo /opt/temp_throttle 58 <- this is important, because over 60 degrees, n7 will poweroff



kde-auto-rotate -> readme to install for rotation with sensors

[URL unfurl="true"]https://www.mediafire.com/file/pvfqfm2zee84xzz/[/URL]



mobile-config-firefox



# git clone https://gitlab.com/postmarketOS/mobile-config-firefox.git



# sudo make install



***Backup full filesystem boot and rootfs



Connect Nexus 7 to PC/Laptop using micro-usb cable, enter TWRP recovery mode → Advance → Terminal



# df



# umount /dev/block/mmcblk0p-- <- fill number here (grouper: 09 or tilapia: 10)



On PC/Laptop



# adb start-server



Backup boot: # sudo adb pull /dev/block/mmcblk0p2 /path/to/boot-kernel-5.14-rc3-next-grate.img



Backup rootfs for grouper(wifi): # sudo adb pull /dev/block/mmcblk0p9 /path/to/rootfs.img



Backup rootfs for tilapia(3G): # sudo adb pull /dev/block/mmcblk0p10 /path/to/rootfs.img



Backup full: # sudo adb pull /dev/block/mmcblk0 /path/to/full_backup_mmcblk0.img
