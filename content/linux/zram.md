+++
date = '2025-04-03T17:04:55+07:00'
draft = false
title = 'Setting up zram in Artix Linux'
+++

Here is the step for configuring zram in Artix Linux


1. Create /etc/modules-load.d/zram.conf 
```sh 
zram
```
2. Create /etc/modprobe.d/zram.conf
```sh 
options zram num_devices=1
```
3. Create /etc/udev/rules.d/10-zram.rules
{{< code language="bash" >}}
ACTION=="add", KERNEL=="zram0", ATTR{initstate}=="0", ATTR{comp_algorithm}="zstd", ATTR{disksize}="4G", RUN="/usr/bin/mkswap -U clear %N"
{{< /code >}}

4. Finally, add zram to fstab for automount
Edit /etc/fstab
```sh
/dev/zram0 none swap defaults,discard,pri=100 0 0
```
5. Reboot to take the effect immediately

6. After reboot, Check output with 
```sh
zramctl 
```
7.  *Voila!!*

Reference link :
https://wiki.archlinux.org/title/ZRAM

https://wiki.gentoo.org/wiki/Zram