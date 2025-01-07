# Configuring [Basic] Touch Panel with Ethernet/IP

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

## Steps
1. Download and install Visu+2 Express
2. Open Visu+2 Express and start a new project with the BTP
3. Add the _RockWell Automation > Allen Bradley EthernetIP_ driver
![image](https://github.com/user-attachments/assets/a525071d-54de-4ad9-b0db-84cdc63d80f2)
4. Go to _Comm. I/O Driver Settings_
![image](https://github.com/user-attachments/assets/ac9c84b6-0790-49b2-a28c-2f93d7c4283f)
5. Create the station
![image](https://github.com/user-attachments/assets/524d1546-7b9c-4df9-bd70-ae95d1cbc668)
6. Test the connection to the PLC
![image](https://github.com/user-attachments/assets/af35e46f-5b0b-4724-bab1-a598aad044a0)
7. Read the tags from the PLC
![image](https://github.com/user-attachments/assets/19a9391e-4150-4ce0-a954-0e2775c5f2d4)
![image](https://github.com/user-attachments/assets/bfe03184-0203-4763-afed-5064a8f1c9fe)
8. Import tags into the project
![image](https://github.com/user-attachments/assets/f6dcac4b-920c-4f86-a981-c47b1480fa48)
9. Create and Download the project to the HMI
![image](https://github.com/user-attachments/assets/d60c6f6e-2f65-4e86-a690-1c0e754e1dde)
