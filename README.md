Ubuntu 18.04 LTS Minimal Image
------------------------------

These are some experiments, evaluations and random thoughts with mainline kernel on H5 boards.
It's a Work In Progress (WIP), kernel 4.15 and up will be updated from time to time.


| SBC Board tested       |   kernel version       |  gcc version   |   display   /  Touch ID     | idle Min / Full Max Temp ºC |   RAM Memory usage   | Gbps / Fast ehternet |       Wifi       |    BT      |     Issues              |    
|------------------------|------------------------|----------------|-----------------------------|-----------------------------|----------------------|----------------------|------------------|------------|-------------------------|
|                        |   kernel 4.17.rc4      |    7.2.1       |2.8" ILI9341                 |                             |                      |                      |                  |            | USB hid regression (*)  |
|                        |   kernel 4.17.rc1      |    7.2.1       |2.8" ILI9341                 |                             |                      |                      |                  |            |                         |
|                        |   kernel 4.16.8        |    7.2.1       |2.8" ILI9341                 |                             |                      |                      |                  |            |                         |
|                        |   kernel 4.15.18 (EOL) |    7.3.0       |2.8" ILI9341                 |                             |                      |                      |                  |            |                         |
|                        |   kernel 4.14.30       |    7.2.1       |2.8" ST7789S / ADS7846 touch |                             |                      |                      |                  |            |                         |


Wiring 2.8" TFT display on the board
------------------------------------





To Do
-----
* Conduct and document some of the experiments
