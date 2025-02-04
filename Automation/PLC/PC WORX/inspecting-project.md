# Inspecting a Project using PC WORX
This example will be done using the ILC 171 but any PC WORX PLC will work the same.
To interrogate and inspect the application in the ILC 171 controller would be possible __only if the project files were downloaded to the PLC__.

ILC 171 can be programmed and configured by using PC WORX (license required) software or its limited version PC WORX Express (no license required). Both software are contained in the AUTOMATIONWORX Software Suite 1.89 from Phoenix Contact. This can be downloaded from Phoenix Contact website >> Downloads >> Software >> [AX_SW_Suite_2022_189.zip - PC WORX](https://www.phoenixcontact.com/en-au/products/programming-pc-worx-basic-lic-2985275). If it doesn’t work, you will need to download an older version (you can find it in the software archive).

Once PC WORX Express has been installed, please confirm if the controller application can be accessed by following the next steps:
1. Open PC WORX Express – Please make sure one instance is running at the time, second instance will run as a Restricted (read only) mode.

![image](https://github.com/user-attachments/assets/332ac656-bdc9-4b29-b9d0-f63c10aa69de)

2. Create new project > File > New Project > select the ILC 1xx tab > scroll down to find the controller with same HW/FW as physical unit. To verify the controller HW/FW please check at front of it under ILC 171 ETH 2TX label. Press OK button

![image](https://github.com/user-attachments/assets/2fbe6468-07f8-4cb8-bfe8-6ca96350135f)

3. Click “Bus Configuration” button to set controller IP address.

![image](https://github.com/user-attachments/assets/005f3d27-08b1-4767-9483-957dabfcd420)

4. Click on ILC 171 ETH 2TX under _Bus Structure_ section.

![image](https://github.com/user-attachments/assets/f3c6c2b8-ed80-47c8-bdca-f00448b60e94)

5. Click on Communication tab

![image](https://github.com/user-attachments/assets/05d53299-084e-4eeb-8738-3d26299fb624)

6. Enter IP Address, Subnet Mask and press the Test button – You will get a green message over Resource tab when communication with controller has been established.

![image](https://github.com/user-attachments/assets/1490aac1-3b4d-4fd4-8d9b-b624dd31f23a)

7. Proceed with doing click on Build >> Make to set this new IP address in the Project > it should display not errors under Message Window.

![image](https://github.com/user-attachments/assets/f9121f83-c825-40e5-b488-c6bd18478991)
![image](https://github.com/user-attachments/assets/6e91c2c9-39dd-4398-8c67-cf6937added3)

8. Click on Project Control Dialog button > new screen will come up as per below.

![image](https://github.com/user-attachments/assets/2094670c-1507-4be7-aa80-e1369d530db7)
![image](https://github.com/user-attachments/assets/aebed329-b957-4d9a-a684-584a0a71784d)

9. As it was mentioned at beginning of this guide, only the application can be accessed if the project files were downloaded. In saying this, please check the Upload button in that window. If the Upload button is greyed out, that indicates that files were not downloaded, and application cannot be accessed.

![image](https://github.com/user-attachments/assets/fc6c5ab5-5c55-484a-8062-f83bd5996485)
Otherwise, a Zipped file can be downloaded - Uploads the zipped project source from the PLC. __Only available, if project sources have been downloaded before__. The zipped project source, which has been downloaded as a backup to the PLC, can be uploaded to be viewed or edited. The dialog 'Upload' appears, in which you have to confirm the upload process for the current resource. Click 'Project Source'. The project source will now be loaded from the resource to the programming system and automatically unzipped into a new project named 'Untitled'. (If a project is currently open, this project will be closed first). The status bar displays the progress of the upload process.

10. You can get information about the controller status and the POUs using the Info button – This is only as information, not accessing the code.

![image](https://github.com/user-attachments/assets/f50a9070-b31b-43aa-8cd7-8938a8e45c5d)
![image](https://github.com/user-attachments/assets/0b3443f9-2f36-42d5-aa66-958c0d96e0d2)

