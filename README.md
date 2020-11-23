# Thorlabs KBD101
```
kaz@kaz-desktop:~$ lsusb
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 007 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 006 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 005 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 003 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub

{ Connnected KBD101 with DDSM100 stage }
kaz@kaz-desktop:~$ lsusb
Bus 002 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 007 Device 002: ID 0403:faf0 Future Technology Devices International, Ltd Brushless Motor Controller
Bus 007 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 006 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 005 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 004 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
Bus 003 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
```


## usb-devices
```
kaz@kaz-desktop:~$ usb-devices 

T:  Bus=07 Lev=01 Prnt=01 Port=01 Cnt=01 Dev#=  3 Spd=12  MxCh= 0
D:  Ver= 2.00 Cls=00(>ifc ) Sub=00 Prot=00 MxPS= 8 #Cfgs=  1
P:  Vendor=0403 ProdID=faf0 Rev=10.00
S:  Manufacturer=Thorlabs
S:  Product=Brushless Motor Controller
S:  SerialNumber=28000335
C:  #Ifs= 1 Cfg#= 1 Atr=c0 MxPwr=0mA
I:  If#=0x0 Alt= 0 #EPs= 2 Cls=ff(vend.) Sub=ff Prot=ff Driver=ftdi_sio
```

## dmesg
```
[150408.618149] usb 7-2: new full-speed USB device number 2 using uhci_hcd
[150408.843193] usb 7-2: New USB device found, idVendor=0403, idProduct=faf0, bcdDevice=10.00
[150408.843196] usb 7-2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[150408.843198] usb 7-2: Product: Brushless Motor Controller
[150408.843200] usb 7-2: Manufacturer: Thorlabs
[150408.843201] usb 7-2: SerialNumber: 28000335
[150408.931176] usbcore: registered new interface driver usbserial_generic
[150408.931188] usbserial: USB Serial support registered for generic
[150408.937928] usbcore: registered new interface driver ftdi_sio
[150408.938507] usbserial: USB Serial support registered for FTDI USB Serial Device
[150408.938723] ftdi_sio 7-2:1.0: FTDI USB Serial Device converter detected
[150408.938851] usb 7-2: Detected FT-X
[150408.943577] usb 7-2: FTDI USB Serial Device converter now attached to ttyUSB0
[151019.468512] usb 7-2: USB disconnect, device number 2
[151019.473841] ftdi_sio ttyUSB0: FTDI USB Serial Device converter now disconnected from ttyUSB0
[151019.473883] ftdi_sio 7-2:1.0: device disconnected
[153611.691507] usb 7-2: new full-speed USB device number 3 using uhci_hcd
[153611.919525] usb 7-2: New USB device found, idVendor=0403, idProduct=faf0, bcdDevice=10.00
[153611.919529] usb 7-2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[153611.919531] usb 7-2: Product: Brushless Motor Controller
[153611.919534] usb 7-2: Manufacturer: Thorlabs
[153611.919536] usb 7-2: SerialNumber: 28000335
[153611.929612] ftdi_sio 7-2:1.0: FTDI USB Serial Device converter detected
[153611.929660] usb 7-2: Detected FT-X
[153611.933682] usb 7-2: FTDI USB Serial Device converter now attached to ttyUSB0
[153797.092491] audit: type=1400 audit(1602429023.016:6535): apparmor="DENIED" operation="open" profile="snap.snap-store.ubuntu-software" name="/var/lib/snapd/hostfs/usr/share/fonts/" pid=1834 comm="snap-store" requested_mask="r" denied_mask="r" fsuid=1000 ouid=0
[153797.092778] audit: type=1400 audit(1602429023.016:6536): apparmor="DENIED" operation="open" profile="snap.snap-store.ubuntu-software" name="/var/lib/snapd/hostfs/usr/share/fonts/" pid=1834 comm="snap-store" requested_mask="r" denied_mask="r" fsuid=1000 ouid=0
[153797.092923] audit: type=1400 audit(1602429023.016:6537): apparmor="DENIED" operation="open" profile="snap.snap-store.ubuntu-software" name="/var/lib/snapd/hostfs/usr/share/fonts/" pid=1834 comm="snap-store" requested_mask="r" denied_mask="r" fsuid=1000 ouid=0
```

## Block devices
```
kaz@kaz-desktop:~$ lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
loop0    7:0    0 146.5M  1 loop /snap/code/43
loop1    7:1    0 217.9M  1 loop /snap/gnome-3-34-1804/60
loop2    7:2    0 146.5M  1 loop /snap/code/47
loop3    7:3    0    55M  1 loop /snap/core18/1880
loop4    7:4    0 255.6M  1 loop /snap/gnome-3-34-1804/36
loop5    7:5    0  43.2M  1 loop /snap/snap-store/415
loop6    7:6    0 162.9M  1 loop /snap/gnome-3-28-1804/145
loop7    7:7    0  96.6M  1 loop /snap/core/9804
loop8    7:8    0  49.8M  1 loop /snap/snap-store/467
loop9    7:9    0  55.3M  1 loop /snap/core18/1885
loop10   7:10   0  62.1M  1 loop /snap/gtk-common-themes/1506
loop12   7:12   0  29.9M  1 loop /snap/snapd/8790
loop13   7:13   0  30.3M  1 loop /snap/snapd/9279
loop14   7:14   0  97.1M  1 loop /snap/core/9993
sda      8:0    0  74.5G  0 disk 
├─sda1   8:1    0   512M  0 part /boot/efi
├─sda2   8:2    0     1K  0 part 
└─sda5   8:5    0    74G  0 part /
sdb      8:16   0 931.5G  0 disk 
└─sdb1   8:17   0 931.5G  0 part 
sr0     11:0    1  1024M  0 rom  
kaz@kaz-desktop:~$ blkid
/dev/sda5: UUID="9eb2dbe7-6aed-45da-a034-490124b2e86c" TYPE="ext4" PARTUUID="c4325a14-05"
```

