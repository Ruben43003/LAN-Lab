# LAN-Lab
In this project I built an at home lab constructed on cisco packet tracer to test and troubleshoot network connectivity. The LAN uses 4 "2960-24TT" switches and 1 "1841" router. Each endpoint device is connected through copper wire and was dynamically assigned an IP address through the dhcp service configured on the 1842 router.

![LAN-Overview](https://i.imgur.com/mvFzWNV.png)

After setting up the LANs logical topology I statically assigned the router an IP address of 192.162.0.1 and proceeded to configure it through the CLI commands. DHCP service was enabled and the router was given a pool of addresses ranging from 192.162.0.2 - 192.162.0.20 with a lease time of 8 days. 

# Configuring DHCP
I set up the routers DHCP service using CLI commands and here are the specific commands I used to set up an address pool of 192.162.0.2 -192.162.0.20


- configure terminal
- ip dhcp excluded-address 192.162.0.1
- ip dhcp pool MY_POOL
- network 192.162.0.0 255.255.255.0
- default-router 192.162.0.1
- dns-server 8.8.8.8
- lease 8
- address 192.162.0.2 192.162.0.20 


# Testing and confirming Network connectivity

Once the devices each recieved an IP address, network connectivity was tested by opening CMD on PC2 (192.162.0.4) and pinging the IP address of PC3 (192.162.0.3).  4 successful pings were returned, therefore proving the devices on my wired network were able to communicate. 

![Ping](https://i.imgur.com/QFZT2Bl.png)






