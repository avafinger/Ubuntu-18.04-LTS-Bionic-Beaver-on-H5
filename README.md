Ubuntu 18.04 LTS Minimal Image
------------------------------

These are some experiments, evaluations and random thoughts with the mainline kernel on H5 boards.
It's a Work In Progress (WIP), kernel 4.15 and up will be updated from time to time.
The goal here is to test the mainline status to the chosen board sample and not the board features.
Chose a dev board specific to your needs and a kernel version to work best with the chosen board.

The table below shows the first run and values gathered are not final, YET.

|  SBC Dev Board sample  |      NEO2             |      NEO2             |      NEO2             |      NEO2             |      NEO2             |      NEO2             |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |   4.17.rc5            |    4.17.rc4           |    4.17.rc1           |     4.16.8            |     4.15.18           |    4.14.30            |
| gcc version            |     7.3.0             |     7.2.1             |     7.2.1             |     7.2.1             |     7.3.0             |     7.2.1             |
| display / Touch IC     | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 2.8" TFT ILI9341      | 
| graphical interface    | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           |
| power regulator IC     | none in this revision | none in this revision | none in this revision | none in this revision | none in this revision | none in this revision |
| idle Temp ºC / freq    | NA  (*)               | NA (*)                | NA (*)                | 29 ºC / 480 Mhz       | 28 ºC / 480 Mhz       | 26 ºC (*)             |
| full Temp ºC / freq    | NA  (*)               | NA (*)                | NA (*)                | 39 ºC / 1008 Mhz      | 39 ºC / 1008 Mhz      | 39 ºC / 1008 Mhz      |
| RAM memory usage (avg) | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 46 Mbytes             | 44 Mbytes             |
| Wifi                   | none                  | none                  | none                  | none                  | none                  | none                  |
| BT                     | none                  | none                  | none                  | none                  | none                  | none                  |
| issues                 | none                  | USB hid regression    | none                  | none                  | none                  | none                  |

(*) Could not get statistics and values from kernel

  

|  SBC Dev Board sample  |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |      NEO Plus2        |
|------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| kernel version         |   4.17.rc5            |    4.17.rc4           |    4.17.rc1           |     4.16.8            |     4.15.18           |    4.14.30            |
| gcc version            |     7.3.0             |     7.2.1             |     7.2.1             |     7.2.1             |     7.3.0             |     7.2.1             |
| display / Touch IC     | 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 2.8" ST7789S / ADS7846| 
| graphical interface    | framebuffer           | framebuffer           | framebuffer           | framebuffer           | framebuffer           | X11 / Desktop         |
| power regulator IC     | SY8106                | SY8106                | SY8106                | SY8106                | SY8106                | SY8106                |
| idle Temp ºC / freq    | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   |
| full Temp ºC / freq    | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   |
| RAM memory usage (avg) | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   | WiP                   |
| Wifi                   | not tested            | not tested            | not tested            | not tested            | not tested            | not tested            |
| BT                     | not tested            | not tested            | not tested            | not tested            | not tested            | not tested            |

  

|  SBC Dev Board sample  |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |      K1 Plus          |
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
* BPI-Zero H5 availability is Unknown according to Nora Lee from FoxConn.
* OrangePi board samples have been held by Customs (bad luck), but there are plenty of distro out there, but would be nice to have one with SY8106 just to compare.


Wiring 2.8" TFT display to the boards
-------------------------------------

* to be completed

  

Building Ubuntu 18.04 LTS minimal image
---------------------------------------

* to be completed

  
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
