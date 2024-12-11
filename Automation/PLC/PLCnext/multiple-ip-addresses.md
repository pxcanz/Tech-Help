# Multiple IP Addresses on PLCnext
This can be useful when needing to have multiple IP addresses on the same interface. 
For example, if a PLC is on the network but needs to talk through MODBUS on another IP address.

To add another IP address, it needs to be done through command line. [This reference](https://askubuntu.com/questions/313877/how-do-i-add-an-additional-ip-address-to-etc-network-interfaces) was used.

Follow these steps to configure:

1. Login to the PLCnext using SSH
2. Type `ip addr` to see the current network configuration
3. Type `nano /etc/network/interfaces` which will allow you to edit the interfaces
4. Press CTRL-X to exit
5. Type `y` to confirm
6. Press ENTER to confirm the file to save it as (it should match for it to overwrite and work)
7. Type `sudo reboot` to reboot the PLC
8. Once the PLC is online, run the command `ip addr` again to see the interfaces.

Below you can see an example of this file configured with two IP addresses on one interface.
```
auto eth0

iface eth0 inet static
address 192.168.1.10
netmask 255.255.252.0
gateway 192.168.1.1
dns-nameservers 8.8.8.8 8.8.4.4

# addition here   #
auto eth0:0
iface eth0:0 inet static
address 192.168.2.10
netmask 255.255.255.0
# End of addition #

auto enp1s0
iface enp1s0 inet static
address 192.168.2.10
netmask 255.255.255.0
gateway 192.168.2.1
dns-nameservers 8.8.8.8 8.8.4.4
```
