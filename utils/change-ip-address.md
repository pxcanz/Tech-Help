# Changing IP Address
With Windows and the fact that changes are made often with different releases, I will try and provide steps that will work on multiple releases with the least number of steps.
Changing the IP address on a Windows computer is a common requirement for connecting to PLCs and other devices.
## Determining IP Address to change your PC to
Again, there are multiple solutions to this but I will provide the most common way this is achieved. If you know someone that knows the network, or how to connect to the PLC, ask them "What should I make my IP address on my computer" or "What IP address is free that I can change my PC to?". This is usually the quickest way.

A couple of things with this. We hit a bit of a paradox: you can only connect to the PLC when your PC has an IP address on the network but you can't have two IP addresses the same on the same network. This is where the above step is much easier for finding an IP address. If that is not going to work, sometimes it is trial and error, 
sometimes there is only a couple of devices that are potential conflicts.

I am assuming, like most, that the network has a subnet of `255.255.255.0` - it is a pretty good assumption if you are unsure. (If it is not this, you probably know how to set up your PC already and you aren't reading this).

If the PLC (device) is 192.168.1.10 and that is the only device plugged into your the ethernet port of the PC, then it is simple, you can change your IP address to be 192.168.1.11 or any number between 192.168.1.1 to 192.168.1.254 __but not 192.168.1.10__. (You will also likely not need to worry about a default gateway, if you do, you probably are not reading this. But if for some reason you do, it is the address of the device that can connect you to other networks or commonly - the internet.)
## Configuring your PC settings
1. Press WIN-R to bring up the _Run_ Window. Alternativaly you can search for _Run_ in the start menu.

![Screenshot 2024-12-11 111926](https://github.com/user-attachments/assets/149b246f-ea1c-45fc-9cdc-8f8c21cb7e40)

2. Type in `ncpa.cpl` and press _OK_

![Screenshot 2024-12-11 112054](https://github.com/user-attachments/assets/70012146-95d8-4ffa-a60b-94ace4b79732)

3. You will see multiple adapters as shown above. You can plug and unplug the device (PLC) from your PC to determine which one is correct
4. Right click on the adapter you want to change and press _Properties_.
5. Double click on _Internet Protocol Version 4 (TCP/IPv4)_

![Screenshot 2024-12-11 112301](https://github.com/user-attachments/assets/8d8191e5-e71b-44bf-8611-8adc62913a4c)

6. Change the address accordingly

![Screenshot 2024-12-11 112345](https://github.com/user-attachments/assets/40e86107-d3c1-45bc-b38d-d3c1580f4d07)

## Confirm connection to PLC
1. Open up command prompt by entering `cmd` into your start menu
2. type in `ping <ip-address>`. Going off the example above it would be `ping 192.168.1.10`.

![Screenshot 2024-12-11 113811](https://github.com/user-attachments/assets/8351c110-ec91-43fc-b527-c00b88d849d2)

If you don't get a response (that looks similar to below): 

![Screenshot 2024-12-11 114046](https://github.com/user-attachments/assets/96eef963-b5cd-4cf8-a178-67d6b0522525)

1. Check the cable is connected properly,
2. Check you have typed in the correct IP address for the PLC
3. Type in `ipconfig` into command prompt (and press enter). Check that you can see the configuration you entered. Commonly, if you can't see this, it is because the pop-up windows are not closed to prompt the PC to 'save' the configuration. _Note: there will likely be mutliple, so double check the configuration you look at matches the adapter you changed._

![Screenshot 2024-12-11 114202](https://github.com/user-attachments/assets/92576ac2-5af8-4a4c-8956-c01eba391189)

If something wasn't correct, retry the `ping` command as before. (You can press the up-arrow as needed to save you retyping it.)
