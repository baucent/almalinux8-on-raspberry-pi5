# UPDATE 2024-06-07 : Almalinux 8.10 on Rpi5 now supported!
See 
https://github.com/AlmaLinux/raspberry-pi/issues/40#issuecomment-2154657605

https://github.com/AlmaLinux/raspberry-pi

Disk image for AL8.10 found here
https://repo.almalinux.org/rpi/images/AlmaLinux-8-RaspberryPi-latest.aarch64.raw.xz
<pre>
On the RPi
AL8.10 has kernel-6.6.28 glibc-2.28 (raspberrypi2-kernel4-6.6.28-20240423.v8.1.el8.aarch64)
AL8.9  had kernel-6.1.31 glibc-2.28 (raspberrypi2-kernel4-6.1.31-v8.1.el8.aarch64)
[AL8 on x86_64  has kernel-4.18.0]
</pre>

**Below** can now be ignored

# Note
I have Almalinux 8.9 running on RPi5 and I am documenting
the particular skulduggery required.

See al89-on-rpi5.txt, almalinux89-boot-log.txt and almalinux89-dmesg.txt
<pre>
Almalinux 8.9 on Raspberry Pi 5
===============================

The 8.9 image[1] provided by Almalinux[2] runs perfectly on RPi4 but
the boot code previously in /boot/bootcode.bin has apparently been
moved into the firmware so replacing bootcode.bin with another
generic boot loader (grub? u-boot?) doesn't work with RPi5.

Raspberry Pi OS[3,4] and Ubuntu[5,6] work on RPi5 (I think both due
to Debian[7,8] "bookworm".)

Rather than go to the trouble of working out how Debian etc manage
this I thought I could leverage the working boot process from RaspiOS
to bring up AL89. Both use systemd and would be similar except for
the kernel versions and firmware.


[1] https://repo.almalinux.org/almalinux/8/raspberrypi/images/AlmaLinux-8-RaspberryPi-8.9-20231127.aarch64.raw.xz
[2] https://wiki.almalinux.org/documentation/raspberry-pi.html#about-raspberry-pi
[3] https://www.raspberrypi.com/documentation/computers/os.html
[4] https://downloads.raspberrypi.com/raspios_arm64/images/raspios_arm64-2024-03-15/2024-03-15-raspios-bookworm-arm64.img.xz
[5] https://ubuntu.com/download/raspberry-pi
[6] https://cdimage.ubuntu.com/releases/23.10/release/ubuntu-23.10-preinstalled-desktop-arm64+raspi.img.xz
[7] https://raspi.debian.net/
[8] https://raspi.debian.net/tested-images/

</pre>
