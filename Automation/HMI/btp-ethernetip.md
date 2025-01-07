# Configuing [Basic] Touch Panel with Ethernet/IP

The Basic Touch Panels (BTP) and Touch Panels (TP) can be configured to with different drivers. This guide will show how to configure the Rockwell / Allen Bradley Ethernet/IP driver. In this guide we will be configuring it on a BTP.
For the software in this example, we will be using the free offering of Visu+2 Express however, the licensed Visu+2 can also be used.

## Hardware Overview
The BTPs use Windows CE and come in different sizes. See the table below highlighting differences between the products

| BTP 2000       | BTP 2043W 1050387       | BTP 2070W 1046666       | BTP 2102W 1046667       |
| -------:       | :---------------------:  | :-----------------:       | :-----------------:       |
| Image          | ![](https://caas.phoenixcontact.com/caas/v1/stable/media/263816/full/b85?format=jpg) | ![](https://caas.phoenixcontact.com/caas/v1/stable/media/229372/full/b85?format=jpg) | ![](https://caas.phoenixcontact.com/caas/v1/stable/media/223450/full/b85?format=jpg) |
|   Size         | 4.3 inch                | 7 inch                  | 10.2 inch               |
| Resolution     | 480 x 272 (WQVGA)       | 800 x 400 (WVGA)        | 800 x 400 (WVGA)        |
| Serial Ports   | 1x RS232/422/485        | 1x RS232 + 1x RS422/485 | 1x RS232 + 1x RS422/485 |

The other items are the same between the options given above.
| Description    | Specification           |
| -------------: | ----------------------- |
| Colours        | 16 700 000              |
| Touch Screen   | Analogue Resistive      |
| IP Rating      | Front: IP66 Back: IP20  |
| Op. Temp.      | 0°C - 50°C              |
| Ethernet Ports | 1x 10/100 Mbps          |

## Software Overview
Note that Visu+ is designed to work with certain Firmware versions of the touch panels. Certain Firmware versions are limited to certain touch panel hardware versions. Ensure that the correct version of Visu+ is downloaded.
[Visu+2 Express](phoenixcontact.net/product/2402774) can be downloaded in by navigating to _Downloads > Software (or Software Archive)_. 
