# PLCnext as Ethernet/IP Adapter
## Introduction
PLCnext has many industrial communication protocols inbuilt into the PLCnext Runtime. PLCnext has Ethernet/IP Adapter built-in to the runtime.
This example shows how to integrate the PLCnext into an upstream Ethernet/IP network.

## Steps
There is two options: to use a generic Ethernet module or use the EDS. For using a generic ethernet deivce on RS Logix, make the following configuration:

![image](https://github.com/user-attachments/assets/b01627a9-17a4-4e67-9a6c-d3c0fc3daca2)
![image](https://github.com/user-attachments/assets/2d5c1dab-c873-4392-89ed-871f6a99dfca)

1. Download the EDS device description from the PLCnext controller product page.

![image](https://github.com/user-attachments/assets/7bbf3e8a-6aa8-4124-87eb-1fa5bfccdb6b)

2. Add it to the hardware configuration
3. Writing values to the output array in Rockwell will be reflected in the input array in PLCnext

![image](https://github.com/user-attachments/assets/2433ffa8-c13a-4e88-a4ab-f1b8eb9bda3d)
![image](https://github.com/user-attachments/assets/ed96225e-e6b8-480e-a3bc-1ae25ac1d8e5)
