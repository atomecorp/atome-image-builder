# Disk Layout

```
MBR
|-> s1 FAT Partition
`-> s2 BSD
    `-> a UFS Partition
```

create bootable atomeOS img :

pkg install qemu :
pkg install qemu

Install poudriere and qemu-user-static:
pkg install poudriere qemu-user-static

Enable qemu-user-static in
ee /etc/rc.conf
add:
qemu_user_static_enable="YES"

Type the command :
sudo /usr/local/etc/rc.d/qemu_user_static start

sudo ./eVe_builder amd64
or for an arm image
sudo ./atome_builder arm

then copy to USB using :

sudo dd if=atome-arm.img  of=/dev/da0 bs="1M"


if needded acces the image thru ssh :
login : freebsd
pass : freebsd
Change root pass :
su
the password is :
root
change previous pass:
passwd root


Troubleshooting

freebsd image not not found:
example change :
base_image="FreeBSD-13.0-CURRENT-arm-armv7-GENERICSD-20210107-f2b794e1e90-255641.img"
to :
base_image="FreeBSD-13.0-STABLE-arm-armv7-GENERICSD-20211021-e058d44fda3-247742.img"
