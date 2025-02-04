# PLCnext as Profinet Device
## About Profinet
With its real-time communication capabilities [PROFINET](https://www.profibus.com/technologies/profinet) is the leading Industrial Ethernet protocol for communication between devices in industrial automation systems. It ensures reliable data transmission, supports various network topologies, and provides device configuration and diagnostics.

## Introduction
PLCnext is highly flexible with communication options. This guide will show how the PLCnext can be used as a Profinet device and being able to send Process Data. 
The structure in PLCnext Engineer is similar but a difference in process data array sizes. In this guide, an example integration with TIA Portal will be given.
```
 _______________________                  _______________________
|                       |                |                       |
| Siemens PLC as        |                | PLCnext PLC as        |
| Profinet Controller   |================| Profinet Device       |
|_______________________|                |_______________________|

```
## Steps
1. Ensure Profinet Device is enabled on the PLCnext by going to WBM > System Services
2. Download the GSDML Device Description from the product page of the PLCnext controller
![image](https://github.com/user-attachments/assets/45ac931f-6bef-4374-80ee-12e2e291d197)
3. "Install" the GSDML into TIA Portal
![image](https://github.com/user-attachments/assets/d92043b0-0842-48f9-9126-0fcf9793c804)
4. Insert the PLCnext Controller next to the controller
![image](https://github.com/user-attachments/assets/3806e8dc-874f-421c-b5c6-93ae12e17394)
6. Configure the IP Address and Device Name
![image](https://github.com/user-attachments/assets/f8bdc269-47e1-4f4a-9c7c-2a0e37e981cf)

PLCnext Profinet Device has a 512 byte array for input and output process data
![image](https://github.com/user-attachments/assets/7fa4fa12-8224-4b2e-93cf-9958477f7ec0)

## Example
__TIA Portal__
![image](https://github.com/user-attachments/assets/4db2a4c2-b256-4f1c-9e7c-846a0ad40de7)
![image](https://github.com/user-attachments/assets/eb318ff7-8063-472c-a83e-51abb1ea72cc)

__PLCnext Engineer__
![image](https://github.com/user-attachments/assets/bb59bd97-46ff-4cb7-a20d-1914a72c91fe)
![image](https://github.com/user-attachments/assets/eb48eedb-0421-47e9-836d-f5b1d4b6569c)

