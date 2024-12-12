![image](https://github.com/user-attachments/assets/0abedb8d-dc80-42fd-addd-fe5108eedcbd)# Integrating Ethernet/IP IO Link Master into Ethernet/IP Network
## Overview
The following below is continuing with the [TRIO3-PS/1AC/24DC/10/4C/IOL](https://phoenixcontact.net/product/1252696) to integrate into an Ethernet/IP network. Learn how to read/write Cyclic and Acyclic data from IO-Link devices and eventually send and receive ISDU requests through Allen Bradley (CompactLogix) PLCs. 

Indexed Service Data Units, or ISDUs, refer to the service data units on the IO-Link devices. ISDUs contain information on connected devices, st# atus updates, and configuration settings. The IOL MA8... DI8 provides write access to send ISDU requests to each IO-Link port and read access to ISDU responses from each IO-Link port.  

Additionally, this document assumes the user understands  Ethernet/IP protocol and is familiar with programs like Studio 5000 software.

## Example is using the following items
| Qty. | Order-No.   | Type-Description           | Description                                                                                       |
|------|-------------|----------------------------|---------------------------------------------------------------------------------------------------|
| 1    | 1072839     | IOL MA8 EIP DI8            | Gateway - 8 Channel IO-Link Master with 16 digital inputs that can also be an Ethernet/IP and Modbus TCP/IP Slave |
| 1    | 1252696     | TRIO3-PS/1AC/24DC/10/4C/IOL| Power supply with 4 channel electronic circuit breaker.                                           |
| 1    | 1769-L24ER-QB1B | Allen Bradley CompactLogix PLC | Allen Bradley PLC                                                              |
| 1    | 9324-RLD250ENE | Studio 5000 software       | Software to configure Ethernet/IP data.                                                        |

## Setup
- Connect three wires going from L+, L- and C/Q of TRIO3-PS/1AC/24DC/10/4C/IOL to L+, L- and C/Q of IOL MA8 EIP DI8 Gateway.
- You can use any of the 8 I/O Link ports available on the IOL MA8 EIP DI8 Gateway. In this example, port 6 is used.
- IP Address of the IOL MA8 EIP DI8 is set to 192.168.1.100 so that webserver can be accessed to get the cyclic and acyclic data from TRIO3-PS/1AC/24DC/10/4C/IOL.
- Make sure to set your PC to the same network subnet as the IOL MA8 EIP DI8 Gateway. In this example, network adapter settings on the PC are set to 192.168.1.245
- Verify you can ping the IP Address you have assigned before you proceed further.

## IODD Files and Configuration
Download the IODD file for the IO-Link device(s). For example, the [TRIO3-PS/1AC/24DC/10/4C/IOL](https://phoenixcontact.net/product/1252696) device, download by going to the [product page](https://phoenixcontact.net/product/1252696) under Downloads > Configuration file. Extract the zip once downloaded.

![image](https://github.com/user-attachments/assets/ca56fe9d-4049-4524-bb93-4e5626ccb249)

1. Logon to webserver of IOL MA8 EIP DI8 (put 192.168.1.100 into the browser)
2. Select the _Attached Devices_ tab
3. Click on _UPLOAD FILE_ followed by Choose File and select the .xml IODD file

![image](https://github.com/user-attachments/assets/930bf911-9bf7-4248-af8d-a6ff6069ed6b)

4. Upload the other images as well from the downloaded zip folder

![image](https://github.com/user-attachments/assets/c4d9b2fd-359c-4c34-b2fa-d2a7d2c7e8b4)

You should now see Green LED Flashing next to the I/O Link port on the TRIO3-PS/1AC/24DC/10/4C/IOL which means that communication has been successfully established.

![image](https://github.com/user-attachments/assets/ee66f056-87cb-4283-bd4b-034ffad2a584)

## Cyclic Data (device specific)
This would be status of Channels telling the user whether it is ON or OFF (Process data Input), ability to control channels ON or OFF (Process data Output), monitor flowing (Load) current (Process data Input), monitor rated current set for all channels (Process data Input) and ability to change rated current for all channels (Process data Output)

Process data Input will also give status on DC OK, Status on whether Pout > 90 or Pout < 90, Power supply output voltage and total output current.

### Process Data Input
![image](https://github.com/user-attachments/assets/fad2965c-a106-4dac-aad9-22b213bddd13)

![image](https://github.com/user-attachments/assets/6b517d4a-1cc6-4f1b-8a7d-98a631add11b)

![image](https://github.com/user-attachments/assets/aae4a690-7499-4c0c-b9bc-79a7f4c42949)

Load is only connected to Channel 1 and hence the remaining channels don’t have any flowing current.

![image](https://github.com/user-attachments/assets/0715edbe-482f-46f6-a626-fe291500d4fe)

### Process Data Output
- Go to “Configuration” - > Utilities in the web management of IOL MA8 EIP DI8 Gateway and set the PDO Writes to “Enable”. You need to be logged in as admin with a password to have this capability.

![image](https://github.com/user-attachments/assets/1c8211be-e189-4432-836f-8247d4193404)

- You should now see this option marked in “Red” under process data section

![image](https://github.com/user-attachments/assets/029c269c-c939-4d09-9da6-e809a60b07c7)

- Expand and Set PDO data bytes to 3

![image](https://github.com/user-attachments/assets/36cfbd31-457d-4481-a55c-c1fbbbd655b0)

![image](https://github.com/user-attachments/assets/43d5bac9-09bb-4f25-b0d0-6c0daafeb179)

- Once PDO is set to data bytes to 3, you should see Port status PDO Valid.
- You should now see an edit option in the Process data section following which you can now turn ON/OFF the channels, set the nominal current for channels etc. You need to set PDO valid flag to 1 in order to have this ability.
- 
You can also set Initial channels state on power up whether all channels should be OFF or channels should follow last saved status prior to powering down.

![image](https://github.com/user-attachments/assets/f29cb5bf-4b54-47e6-98d5-a04af1e47698)

![image](https://github.com/user-attachments/assets/5cef3be5-8209-4b07-acf6-edda23569fa5)

ou can also set channel shutdown priority. You can have channels shutdown based on highest channel number or highest current first when total current has exceeded.

![image](https://github.com/user-attachments/assets/a6a62ac8-d23a-4afd-8622-394fa03201e1)

### Acyclic Data
- Go to Attached Devices -> Port 6 and select User role menu from drop down
- Process Input/Output data is also available as part of Acyclic data
- More details in manual from Page 20 onwards

![image](https://github.com/user-attachments/assets/c8a1b80c-8290-4a4c-a54e-8c47403b0cba)
In the image above:
- 16 is the index
- Number in the next column is the subindex. It is 0 when it is blank

You can set device access locks via acyclic data

![image](https://github.com/user-attachments/assets/12c560ed-ce39-4509-a79a-b4948424587a)

- When local Parameterization lock is set to 1, it means rated current for channels cannot be changed directly on the Trio 3 Power Supply electronic circuit breaker.
- When local user interface lock is set to 1, it means state of channels cannot be changed directly on the Trio 3 Power Supply electronic circuit breaker.

You can change the state of channels and set nominal current via acyclic data 

![image](https://github.com/user-attachments/assets/d7a2d193-e6f5-4504-8fa0-72a1ac93f388)

![image](https://github.com/user-attachments/assets/536f7cc4-2104-49b2-9315-9f68ec3a4c01)

You can set Power Supply output voltage and turn OFF the power supply

![image](https://github.com/user-attachments/assets/da7ea6fe-727c-4a86-993f-aeeaacf0b66f)

You can set relay activation events and enable/disable them for certain events. Default status of Relay is closed and will open when an event happens.

![image](https://github.com/user-attachments/assets/cb44cb2e-a8aa-45ff-9a6b-45fe223ea5a7)

You get event status as well. For example, there was a short circuit on Channel 2 for which value is 1 below meaning an event pending and hasn’t been acknowledged yet. Event status will be reported for Overload, defective channels, Pout > 90 etc.

![image](https://github.com/user-attachments/assets/d9279031-7d3e-4f37-91f6-ededcb3f1fce)

### Acyclic data via ISDU Requests
You can also get real time values and set values by issuing ISDU requests as seen below. In this example, we are trying to obtain nominal current for Channel 1 which is 2 meaning 3.8A NEC-2

![image](https://github.com/user-attachments/assets/bb21643e-8771-481d-b9bb-fcddaf2e34dc)

![image](https://github.com/user-attachments/assets/82ed0f96-93fa-4196-95e0-1e0d76ef202b)

You can set a different nominal current for channel 1 for example 4 which would be 6A

![image](https://github.com/user-attachments/assets/3601f751-c4bf-487a-8ae4-44c3942c5124)

![image](https://github.com/user-attachments/assets/b2c117fc-6ca2-4f49-9e7c-d5d928e40efa)

## Integrating Ethernet/IP Communication
Below we will go over how to send/receive ISDU requests to/from Allen Bradley PLC via Ethernet/IP

Open Studio 5000 software and create a new project by picking the appropriate Allen Bradley CompactLogix Controller. In this example, we are using a 1769-L24ER-QB1B.

### Register EDS File
1.	Go under product page of IOL MA8 EIP DI8 (1072839) and download EDS File.

![image](https://github.com/user-attachments/assets/591e8a34-0953-4169-806e-e308d355560c)

2.	In Studio 5000, go to tools -> EDS Hardware Installation tool and register the EDS File

![image](https://github.com/user-attachments/assets/e45b6138-aec1-4f45-9414-f67b7c0d07c3)

3.	Browse and point to the EDS File downloaded and complete the EDS Registration process.

![image](https://github.com/user-attachments/assets/febbafed-96eb-458e-a670-e0dbc6cf2359)

4.	Right click on “Ethernet” and create a new module

![image](https://github.com/user-attachments/assets/2a8b007f-0e3f-4c5e-bee8-fc381fdfbcc5)

5.	Select 1072839 from module type and click on “create”

![image](https://github.com/user-attachments/assets/8575b0c7-dc08-4315-8dc1-769856d452f6)

6.	Assign a name to the module and the correct IP Address for the IOL MA8 EIP DI8 device. In this example, the IP Address of IOL MA8 EIP DI8 is 192.168.100.  IP Address of CompactLogix PLC is 192.168.1.80 (assigned via BootP/DHCP tool)

![image](https://github.com/user-attachments/assets/5760ec26-1f37-453c-9f7f-11893b1c70b5)

7. Click “OK” following which you should see this module under “Ethernet”

![image](https://github.com/user-attachments/assets/1e373dd2-5751-46b4-bbd3-6dfd406699a4)

### Datatypes
1. Right-click on “Data Types” and select “New Data Type…”. This will allow the user to create a User Defined data type to store the necessary information for an ISDU request.

![image](https://github.com/user-attachments/assets/52ee1bf6-2b70-4254-a4f1-6e53ec9240c0)

2. Refer to picture below, to see the information needed to format an ISDU request, these values will be added to our new user defined data type.

![image](https://github.com/user-attachments/assets/0985937c-e894-48bf-9feb-cdac62b8e94d)

3. Create 6 members with the correct data types as seen below

![image](https://github.com/user-attachments/assets/a7a7c39a-9a60-44c9-823a-f83f7e55c3e9)

4. Now, Repeat the process for ISDU Response. Below are the parameters we need for ISDU Response

![image](https://github.com/user-attachments/assets/0accded2-6d9f-4baa-8328-ce95c894d804)

5. Add 6 members with the correct data type as seen below

![image](https://github.com/user-attachments/assets/f9b242aa-3413-4405-9f7a-258ddbd61b2f)

_Note: The ISDUreq and ISDUresp data types allow the user to send and receive a single ISDU request/response. To send and receive multiple ISDU requests/responses we need to create a new data type to store multiple ISDU requests and a new data type to store multiple ISDU responses._
6. Right click on data type, add a new data type and name it as MultipleReq. In this example, we are sending 4 ISDU requests. Create 4 members with data type ‘ISDUReq’ (which was created earlier)

![image](https://github.com/user-attachments/assets/75ecde44-8d45-4774-9ddd-97c63d02da7f)

7. Repeat the process for Multiple Responses. Add a new data type and name it as MultipleResp

![image](https://github.com/user-attachments/assets/307544d8-2a1b-4c54-93b3-6bd2124655d5)

8. Now that you have the user defined data types created, create variables in the controller to store the requests and responses. Right-click on “Controller Tags” and select “New Tag”. Create a variable titled “MultipleReqs” with the data type “MultipleReq” created in the previous section. This variable will store the ISDU requests. Similarly, create a variable titled “MultipleResps” with the data type “MultipleResp”. This variable will store the ISDU responses

![image](https://github.com/user-attachments/assets/d12b179d-2cc2-4060-98db-200a5c361ead)
![image](https://github.com/user-attachments/assets/c61ba451-0e75-40a5-87bf-d7228955aee3)

### Creating a Ladder Logic Program
Create a new ladder logic program. On rung 0 add one normally open contact and a MSG block. The example program names the normally open contact “ISDUTrigger_1” because it will be triggering the ISDU requests. The MSG block will be holding multiple messages, so it is named “MultipleMSG”.

![image](https://github.com/user-attachments/assets/e0b8c223-903c-43c3-9f88-b37f4bd9258f)

Click on the three dots next to MultipleMSG in the rung to configure MSG parameters as seen below. Source Element and Destination Element should be MultipleReqs and MultipleResps which were created to store multiple ISDU requests and responses.

![image](https://github.com/user-attachments/assets/1ee8bac5-1d51-4936-9970-6244ae7de2e4)

Above is the message instruction format. 

_Note: I have used 8 instead of 3 as instance because TRIO3 PS/CB is connected to port 6 of IOL MA8 EIP DI8 device._

![image](https://github.com/user-attachments/assets/8b13d795-0ecb-431f-8118-9892c962c373)

Make sure that the communication path is set correctly

![image](https://github.com/user-attachments/assets/2ffdc10d-cfa7-46e9-91f0-85dd790f7360)

### ISDU Requests and Responses

In this section, we will go over how to send ISDU requests using index and subindex and verify whether the ISDU response is correct. Below, Here the index and subindex info for the parameter we are trying to read.

![image](https://github.com/user-attachments/assets/8161919d-d55c-407d-bcd9-6764417aa9c3)

Below is the ISDU Formatting

![image](https://github.com/user-attachments/assets/21f662e4-ac43-4012-9920-1f33b0f4366d)

Once the project is downloaded to CompactLogix PLC, go online and enter the values as seen below
- Byte swapping is 0
- Read Write data type is 31 in hex. 1 meaning it is read only and 3 meaning it is fixed 16-byte data area. Refer to the picture in previous step.
- Index and subindex are 16 and 0 as per the picture in the first step from TRIO3 manual.
- Data Length is 16.
- Data is applicable only for writes.

![image](https://github.com/user-attachments/assets/a1207c6f-e9f5-435e-84cd-3070a9061d68)

Toggle the ISDUTrigger_1 bit following which MSG instruction should execute and ISDU response should be received.

![image](https://github.com/user-attachments/assets/7b192f8b-2f69-4c3d-870b-f9a7ad0f575e)

You can now see that the data has been successfully received.

![image](https://github.com/user-attachments/assets/b3471c00-9bd1-404d-b9e4-f2b42ad2eef7)

You can verify that this is correct data by logging on to web manager of IOL MA8 EIP DI8 and by sending an ISDU request to TRIO3 via IO Link as seen below

![image](https://github.com/user-attachments/assets/c17bb824-21e5-45c7-868e-c2b30d54e838)

![image](https://github.com/user-attachments/assets/d8f68683-0681-4567-b4fe-0233c944fd1c)

Matches with expected value. 

- Below is how you handle multiple ISDU Requests

![image](https://github.com/user-attachments/assets/22955646-2469-42ae-92a4-79175f945ad5)

- Below is handlind multiple ISDU Responses

![image](https://github.com/user-attachments/assets/37f88dab-5ddf-4f37-98f0-b0d4a9780cd7)

Nominal Current for Channel 1 is 4 meaning 6A and it matches with what we are getting in Studio 5000 above.

![image](https://github.com/user-attachments/assets/38f41692-72f2-4816-8e93-daf81ba19fb9)

Verified again by sending an ISDU requests in the web manager of IOL MA8 EIP DI8 device

![image](https://github.com/user-attachments/assets/c962f8c9-7e5c-4993-b101-7d46a23e2dc8)
