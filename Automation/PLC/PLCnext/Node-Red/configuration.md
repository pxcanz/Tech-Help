# Node-Red on PLCnext
![image](https://github.com/user-attachments/assets/eeab96e0-ccb0-47f0-a9cd-3b7b97f8ea5c)![image](https://github.com/user-attachments/assets/3282343e-1ac1-477b-a387-6ebdab1be3b7)

# Installing Node-Red on PLCnext
There are two predominant ways that Node-Red can be installed on PLCnext. Node-Red is an open-source, low-code javascript based tool that can be used to convert and display data.

Phoenix Contact takes Node-Red and builds an 'app' for PLCnext Runtime. This makes it really simple to install directly onto the PLCnext and it comes preinstalled with nodes such as PLCnext. The only downside is that it is always behind the latest Node-Red builds. 

# Installing Node-Red App
1. Download the Node-RED application from the [PLCnext Store](https://www.plcnextstore.com/permalinks/apps/latest/60002172000507). An x86 version for PLCnext is also built on the PLCenxt Store. _Note: You will need a free account on PLCnext Store to download._
2. Go to [WBM](https://192.168.1.10/wbm) > Administration > PLCnext Apps
3. Install the Node-RED application. When the app is started, it will take ~20mins to properly start. You will find that the PLC will be unresponsive during this time. Once started, it will power cycle fine and it will not take 20mins to boot up again.
4. Navigate on a browser to [https://192.168.1.10:51880](https://192.168.1.10:51880). This is where you can access Node-RED.
5. Right Click on the _IIOT Gateway Connector_ example and disable it.
6. Here is an overview of what it will look like. _Note: debug nodes were just for testing and are not required._
![Node-Red Flow](https://github.com/user-attachments/assets/a84ee0a8-abb1-4abd-82a3-1290c2e21fd0)

# Installing Manually
1. Download and install Balena Engine for PLCnext. Similar method to the first three steps above.
2. SSH into the PLCnext
3. Run `balena-engine run -it -p 1880:1880 --name mynodered --restart always nodered/node-red`

# Install nodes
There are additional add-ons / nodes that can be added to Node-Red. Some of the common examples might include:
- PLCnext
- OPC UA
![image](https://github.com/user-attachments/assets/6e1db3db-3203-4103-b34f-d2449090eb4d)
