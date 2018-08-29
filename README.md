Ubuntu 18.04 LTS Minimal Image
------------------------------

These are some experiments, evaluations and random thoughts with the mainline kernel on H5 boards.
It's a Work In Progress (WIP), kernel 4.15 and up will be updated from time to time.
The goal here is to test the mainline status to the chosen board sample and not the board features.
Chose a dev board specific to your needs and a kernel version to work best with the chosen board.

The table below shows the first run and values gathered are not final, YET.

* NanoPi K1 Plus Desktop OS Image with Mainline Kernel 4.18.5 is available at mega (8GB SD Card) (experimental)

	https://mega.nz/#F!0WZACYyY!8WBEsKzzZaMk63aXHKtuOA


  User: ubuntu     
  Pasw: ubuntu


Credits:
 * FE for the board and initial kernel (K1 Plus)
 * sunxi community (THS, HDMI, mali)
 * Armbian (tips, technical stuff)

Cpu-freq
[![k1 plus cpu-freq kerne l 4.18.5](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/cpu-freq.gif)]


|  SBC Dev Board sample  |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |      4.17.19 EOL      |      4.18.5           |      4.17.rc7         |      4.17.3           |      NA               |      NA               |
| gcc version            |      7.3.1            |      7.3.1            |      7.3.0            |      7.2.1            |      NA               |      NA               |
| display / Touch ID     |    hdmi / 1920x1080   |   hdmi / 1920x1080    |      2.8" TFT ILI9341 |   hdmi / 1920x1080    |      NA               |      NA               |
| graphical interface    |      X11 / Desktop    |      X11 / Desktop    |      framebuffer      |      framebuffer      |      NA               |      NA               |
| power regulator IC     |      SY8106           |      SY8106           |      SY8106           |      SY8106           |      SY8106           |      SY8106           |
| idle Temp ºC / freq    |  25 ºC / ~720 Mhz     |  35 ºC / ~720 Mhz     |  26 ºC / ~720 Mhz     |  33 ºC / ~720 Mhz     |      NA               |      NA               |
| full Temp ºC / freq    |  70 ºC / 1368 Mhz     |  75 ºC / 1368 Mhz (**)|  54 ºC / 1368 Mhz(***)|  68 ºC / 1368 Mhz(***)|      NA               |      NA               |
| RAM memory usage (avg) |      289 Mbytes       |     289 Mbytes        |      55 Mbytes        |      78 Mbytes        |      NA               |      NA               |
| Camera OV5640          |  30 FPS YUV (full HD) |  30 FPS YUV (full HD) |      NA               |      NA               |      NA               |      NA               |
| Wifi                   |      Ok               |      Ok               |      Ok               |      Ok               |      NA               |      NA               |
| BT                     |      none             |      NA               |      NA               |      NA               |      NA               |      NA               |
| issues                 |      none (2)         |      none (2)         |      none             | none                  | none                  | none                  |

(1) Not able to get cpu frequency
(2) Light Desktop, no HW encoding/decoding, usable

[![htop](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/k1plus_desktop.png)]

(*) Still not able to get  /sys/class/thermal/thermal_zone0/temp due to missing THS. (Fixed)

(**) THS added to the kernel, CPU avg freq for the 4 cores = 110% , never gets 400% while compiling the full kernel on board. (Fixed)
Can use 100% of all cores for the tests. (FIXED)

(***) The ambient temp varies along the test and is not a controlled ambient, so it is just for reference.


|  SBC Dev Board sample  |      NEO2             |      NEO2             |      NEO2             |      NEO2             |      NEO2             |      NEO2             |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |   4.17.rc5            |    4.17.rc4           |    4.17.rc1           |     4.16.8            |     4.15.18           |    4.14.30            |
| gcc version            |     7.3.0             |     7.2.1             |     7.2.1             |     7.2.1             |     7.3.0             |     7.2.1             |
| display / Touch IC     | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 
| graphical interface    | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           |
| power regulator IC     | none in this revision | none in this revision | none in this revision | none in this revision | none in this revision | none in this revision |
| idle Temp ºC / freq    | NA  (*)               | NA (*)                | NA (*)                | 29 ºC / 480 Mhz       | 28 ºC / 480 Mhz       | 26 ºC / 480 Mhz  (**) |
| full Temp ºC / freq    | NA  (*)               | NA (*)                | NA (*)                | 39 ºC / 1008 Mhz      | 39 ºC / 1008 Mhz      | 39 ºC / 1008 Mhz (***)|
| RAM memory usage (avg) | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 44 Mbytes             |
| Wifi                   | none                  | none                  | none                  | none                  | none                  | none                  |
| BT                     | none                  | none                  | none                  | none                  | none                  | none                  |
| Gbps / Fast ethernet   | ok / ok               | ok / ok               | ok / ok               | ok / ok               | ok / ok               | ok / ok               |
| issues                 | none                  | USB hid regression    | none                  | none                  | none                  | none                  |

(*) Could not get statistics and values from kernel (**FIXED**)

(**) idle temp is achieved with a simple login from console and ssh login waiting for at least 1 hr.

(***) full temp is achieved with a simple login from console and ssh login waiting for at least 1 hr and building a full kernel on board
Full kernel build takes > 5 hrs on a slow SD CARD.

|  SBC Dev Board sample  |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |   4.17.rc5            |    4.17.rc4           |    4.17.rc1           |     4.16.8            |     4.15.18           |    4.14.30            |
| gcc version            |     7.3.0             |     7.2.1             |     7.2.1             |     7.2.1             |     7.3.0             |     7.2.1             |
| display / Touch IC     | 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 
| graphical interface    | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           | X11 / Desktop         |
| power regulator IC     | gpio-fixed 1v1 / 1v3  | gpio-fixed 1v1 / 1v3  | gpio-fixed 1v1 / 1v3  | gpio-fixed 1v1 / 1v3  | gpio-fixed 1v1 / 1v3  | gpio-fixed 1v1 / 1v3                |
| idle Temp ºC / freq    | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | 27 ºC / 624 Mhz  (**) |
| full Temp ºC / freq    | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | 55 ºC / 1200 Mhz (***)|
| RAM memory usage (avg) | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | 46 Mbytes             |
| Wifi                   | not tested            | not tested            | not tested            | not tested            | not tested            | OK                    |
| BT                     | not tested            | not tested            | not tested            | not tested            | not tested            | not tested            |
| Gbps / Fast ethernet   | ok / ok               | ok / ok               | ok / ok               | ok / ok               | ok / ok               | ok / ok               |
| issues                 | none                  | USB hid regression    | none                  | none                  | none                  | none                  |

**Wifi enabled and in use**

(**) idle temp is achieved with a simple login from console and ssh login waiting for at least 1 hr.

(***) full temp is achieved with a simple login from console and ssh login waiting for at least 1 hr and building a full kernel on board.
Full kernel build takes > 5 hrs on a slow SD CARD.
  

 
Kernel:

	Linux version 4.17.0-rc7-h5 (ubuntu@nanopi-k1-plus) (gcc version 7.3.0 (Ubuntu/Linaro 7.3.0-16ubuntu3)) #1 SMP Mon May 28 11:59:24 UTC 2018

                             
Interfaces:

	eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
	        inet 192.168.254.100  netmask 255.255.0.0  broadcast 192.168.255.255
	        inet6 fe80::1:fcff:fe05:2848  prefixlen 64  scopeid 0x20<link>
	        ether 02:01:fc:05:28:48  txqueuelen 1000  (Ethernet)
	        RX packets 10332  bytes 807119 (807.1 KB)
	        RX errors 0  dropped 0  overruns 0  frame 0
	        TX packets 10198  bytes 1235786 (1.2 MB)
	        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
	        device interrupt 26  
	
	lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
	        inet 127.0.0.1  netmask 255.0.0.0
	        inet6 ::1  prefixlen 128  scopeid 0x10<host>
	        loop  txqueuelen 1000  (Local Loopback)
	        RX packets 84  bytes 6280 (6.2 KB)
	        RX errors 0  dropped 0  overruns 0  frame 0
	        TX packets 84  bytes 6280 (6.2 KB)
	        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
	
	wlan0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
	        inet 192.168.254.104  netmask 255.255.0.0  broadcast 192.168.255.255
	        inet6 fe80::7ec7:9ff:fea5:4611  prefixlen 64  scopeid 0x20<link>
	        ether 7c:c7:09:a5:46:11  txqueuelen 1000  (Ethernet)
	        RX packets 763  bytes 94077 (94.0 KB)
	        RX errors 0  dropped 0  overruns 0  frame 0
	        TX packets 22  bytes 3216 (3.2 KB)
	        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


[![htop](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/htop_rc6.png)]

[![free mem](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/free_rc6.png)]

|  SBC Dev Board sample  |      BPI H5           |      BPI H5           |      BPI H5           |      BPI H5           |      BPI H5           |      BPI H5           |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| gcc version            |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| display / Touch ID     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| graphical interface    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| power regulator IC     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| idle Temp ºC / freq    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| full Temp ºC / freq    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| RAM memory usage (avg) |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| Wifi                   |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| BT                     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |

     

|  SBC Dev Board sample  |      BPI-Zero H5      |      BPI-Zero H5      |      BPI-Zero H5      |      BPI-Zero H5      |      BPI-Zero H5      |      BPI-Zero H5      |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| gcc version            |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| display / Touch ID     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| graphical interface    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| power regulator IC     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| idle Temp ºC / freq    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| full Temp ºC / freq    |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| RAM memory usage (avg) |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| Wifi                   |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |
| BT                     |      NA               |      NA               |      NA               |      NA               |      NA               |      NA               |


* K1 Plus is on the way, thanks to FriendlyElec.


Wiring 2.8" TFT display to the boards
-------------------------------------

Here is the wiring diagram:
[![lcd diagram](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/wiring.png)]

K1 Plus view
[![k1 plus wiring](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/k1.jpg)]

LCD
[![k1 plus lcd](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/ili9341.jpg)]
  

Building Ubuntu 18.04 LTS minimal image
---------------------------------------

**1. Set up your chroot environment**

We need the chroot tools to access the ARM64 Ubuntu Base rootfs from the X86_64 (HOST PC) and add some packages


**2. Get the Ubuntu 18.04 LTS Base files**

	wget http://cdimage.ubuntu.com/ubuntu-base/bionic/daily/current/bionic-base-arm64.tar.gz
 

**3. Find your SD CARD**

Insert the **SD CARD** into USB card reader/writer and check:

	dmesg|tail
	[  181.158588] sd 6:0:0:0: [sdc] 30547968 512-byte logical blocks: (15.6 GB/14.6 GiB)
	[  181.159831] sd 6:0:0:0: [sdc] Write Protect is off
	[  181.159835] sd 6:0:0:0: [sdc] Mode Sense: 03 00 00 00
	[  181.160836] sd 6:0:0:0: [sdc] No Caching mode page found
	[  181.160841] sd 6:0:0:0: [sdc] Assuming drive cache: write through
	[  181.167092]  sdc: sdc1 sdc2
	[  181.170832] sd 6:0:0:0: [sdc] Attached SCSI removable disk
	[  182.194865] EXT4-fs (sdc1): mounted filesystem with ordered data mode. Opts: (null)
	[  182.202709] EXT4-fs (sdc2): mounted filesystem without journal. Opts: (null)
	

The SD CARD is in the format /dev/sdX where X is a letter (b,c,....), in our case is c (from above)

	sd card is /dev/sdc


**4. Format *SD CARD* with specific geometry**

	sudo ./format_sd.sh /dev/sdc


**5. Prepare the *SD CARD* with Ubuntu 18.04 LTS Minimal Rootfs**

Change the SDCARD=/dev/sdX (our sd card device) to your /dev/sdX (X is your device letter)

	sudo su
	export SDCARD=/dev/sdc
	mkdir -p rootfs
	mount $SDCARD"2" rootfs


**6. Decompress the rootfs**

	tar -xvpzf ./bionic-base-arm64.tar.gz -C ./rootfs --numeric-ow
	sync


**7. Prepare the SD CARD to chroot**

	cp /usr/bin/qemu-aarch64-static ./rootfs/usr/bin/
	cp /usr/bin/qemu-arm-static ./rootfs/usr/bin/
	sync


**8. Prepare chroot to add some needed packages**

	cp -fv /etc/resolv.conf ./etc/resolv.conf
	cp -rvf ./etc/* ./rootfs/etc
	sync


**9. Update our SD CARD with the pre-built kernel**

	mkdir -p ./rootfs/lib/modules
	sudo tar -xvpzf kernel.tar.gz -C ./rootfs/lib/modules --numeric-ow
	sync
	mkdir -p ./rootfs/lib/firmware
	sudo tar -xvpzf firmware.tar.gz -C ./rootfs/lib/firmware --numeric-ow
	sync


**10. Chroot to SD CARD and add networking**

	chroot ./rootfs /bin/bash
	apt-get install dialog kmod ifupdown net-tools apt-utils pkg-config sudo systemd udev iputils-ping init


	
*This will be the minimum packages nd if you want a bit more like dev tools and console fonts, install ubutu-minimal*

	
	apt-get install ubuntu-minimal

	
 	
*if you want to login with *ssh* then install it*


	apt-get install ssh
	sync
	exit (*Exit from chroot*)



Now we need to be able to login as **root** without password, do in shell:

**11. Edit with your preferred editor the file ./rootfs/etc/passwd**

Change the line from

	root:x:0:0:root:/root:/bin/bash

to

	root::0:0:root:/root:/bin/bash

and save

**11. Edit with your preferred editor the file ./rootfs/etc/shadow**

Note: not sure this is **really** necessary!!

Change the line from

	root:*:17392:0:99999:7:::

to

	root::17392:0:99999:7:::

and save

**12. Add the "ubuntu" user, or your own user - IF YOU WANT**

	addgroup --gid 1000 ubuntu
	adduser --uid 1000 --gid 1000 ubuntu
	usermod -a -G adm ubuntu
	usermod -a -G cdrom ubuntu
	usermod -a -G sudo ubuntu
	usermod -a -G dip ubuntu
	usermod -a -G plugdev ubuntu
	usermod -a -G bluetooth ubuntu
	usermod -aG sudo ubuntu
	groupadd ubuntu
	useradd -m -g adm -G root,sudo,users,audio,video,netdev,plugdev -s /bin/bash ubuntu
	echo "ubuntu" >> passwd ubuntu


**13. Unmount the partition**

	umount ./rootfs
	sleep 1
	rm -rf ./rootfs


**13. Prepare the Boot**

	mkdir -p boot
	mount $SDCARD"1" boot
	sleep 1
	sudo tar -xvpzf boot.tar.gz -C ./boot --numeric-ow
	sync
	sleep 1
	umount ./boot
	sleep 1
	rm -rf ./boot


*Prepare the booloader*

	sudo dd if=spl/sunxi-spl.bin of=/dev/sdc bs=1024 seek=8
	sync
	sudo dd if=u-boot.itb of=/dev/sdc bs=1024 seek=40
	sync


Exit from **su** (root)

	exit

**14. We have now our Ubuntu 18.04 LTS Image on SD CARD**

	Just make sure the SD CARD is unmounted and remove it from the USB reader/writer


  
Screenshots
-----------

* kernel 4.17.0-rc5 (framebuffer)

[![arm64 screenshot](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/kernel_4.17.rc5.png)]

[![arm64 screenshot](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/kernel_4.17.rc5_mc.png)]

[![arm64 screenshot](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/kernel_4.17.rc5_htop.png)]


* X11 / Desktop

[![arm64 screenshot desktop](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/desktop-1.png)]

[![arm64 screenshot desktop](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/desktop-2.png)]

[![arm64 screenshot SDL](https://github.com/avafinger/Ubuntu-18.04-LTS-Bionic-Beaver-on-H5/raw/master/img/ballfield-2.png)]



To Do
-----
* To Conduct and document some of the experiments
