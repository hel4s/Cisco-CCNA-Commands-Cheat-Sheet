# Cisco-Commands-Cheat-Sheet
Here you can find the CISCO cli commands you have to learn for the CCNA.



# CISCO Modes
| Mode | Description | 
|:----------:|:-------------:|
Router> | User mode
Router# | Privilege mode
Router(config)# | Global Config mode 
Router(config-if) | Interface mode
Router(config-vlan)# | Vlan config mode
Router(config-router)# | router config mode



# Basic Commands

| Command  | Purpose | 
|:----------:|:-------------:|
 `enable`| Enters privilege mode 
 `configure terminal` | Enters configuration mode
 `description` *<name-string>* | Sets a description to the interface
`hostname` *name* | Sets a host name to the current Cisco network device
`interface` *fastethernet/number* | Enters interface configuration mode for the specified fast ethernet interface
`copy` *from-location to-location* | copie a file (or set of files) from one location to another
`copy running-config startup-config` | It saves the configuration when the device reloads, it loads the latest configuration file
`copy startup-config running-config` | Saves the startup configuration into the running configuration
 `write` | Save the current configuration
 `write erase` / `erase startup-config` | Deletes the startup config
`reload` | 	Reboots the device
 `exit` / `end` | Returns to previous mode 
 `logout`/ `disable` | 	Exit User mode
 `shutdown` |  Shuts down the interface
 `no shutdown` | turns up the interface
 
 # Basic show Commads
 | Command  | Purpose | 
 |:----------:|:-------------:|
 `show running-config` | Displays the current configuration
 `show startup-config` | Displays the configuration at startup
 `show interfaces` | Displays detailed information about interface status
 `show ip protocols` | Displays all the configured routing protocols 
 `show ip interface` |  Displays the status for each interface
 `show interface status` | Displays the interface line status
 `show mac address-table` | Displays the MAC address table



 
# Vlan Configuration Commands 
  | Command  | Purpose | 
|:----------:|:-------------:|
`vlan` *vlan-id* | Enter to configuration vlan mode
`show vlan/ show vlan brief` | Lists each VLAN and all interfaces assigned to that VLAN but does not include trunks
`switchport mode trunk` |  Set the interface  link type as a trunk link 
`show interfaces trunk` |  Displays information about the operational trunks along with their VLANs
`switchport trunk encapsulation dot1q` | 	Sets the 802.1Q encapsulation on the trunk port

 
 
 # RIP Configuration Commands 
  | Command  | Purpose | 
|:----------:|:-------------:|
 `router rip` | Enters RIP configuration mode
 `version 2` | RIP version 2 
 `no auto-summary` | Modifys the default RIPv2 behavior of automatic summarization
 `show ip rip database` | Displays the contents of the RIP routing database

 
 
 # EIGRP Configuration Commands 
  | Command  | Purpose | 
|:----------:|:-------------:|
 `router eigrp <Autonomous system number> ` | Enters EIGRP config mode 
 `eigrp router id` | Configures EIGRP router ID
 `no auto-summary ` | Modifys the default EIGRP behavior of automatic summarization
 `show ip eigrp neighbors` |  Disables EIGRP neighbors 
 
 
 # OSPF Configuration Commands 
 | Command  | Purpose | 
|:----------:|:-------------:|
 `router ospf ` *number* | Enters OSPF config mode
 `passive-interface` *interface* | Stops sending 'Hello' messages of the specified interface
 `router-id` *number* | Sets an OSPF router ID in ip format 
 `clear ip ospf` | Rests OSPF
 `auto-cost bandwidth` *megabits per second* | Change the refrence bandwidth
 `ip ospf cost`  *cost*| Manually configure the OSPF cost 
 `ip ospf [process-id] area [area]`  | Activates OSPF on an interface
 `ip priority [Priority]` | Changes the OSPF interface priority 
 `ip ospf process` | Rests the OSPF process
 `ip ospf network` *type* | Manually configure the network type 
 `ip ospf database` |  Displays the contents of the OSPF routing database
 `bandwidth` *<bandwidth in kilobits>* | Changes the interface bandwidth 
 `show ip interface ospf` *brief* | Disables each OSPF-enabled interface
 `show ip ospf interface`  *interface* |  Displays the specified OSPF interface
 `show ip ospf neighbor` | Disables OSPF neighbors 
 

# HSRP Configuration Commands 
 | Command  | Purpose | 
|:----------:|:-------------:|
 `standby` *group number* | Configures HSRP
 `standby version 2` | HSRP version 2 
 `standby <group number> ip` *IP address* | Configures the virtual IP address
 `standby <group number> priority` *value* | Manually configure the active router
 `standby <group number> preempt` | Enables preemption
 `show standby` | Displays global information for HSRP
 
 

# STP Configuration Commands 
| Command  | Purpose | 
|:----------:|:-------------:|
 `spanning-tree portfast` | Enables portfast
 `spanning-tree portfast bpdguard default` | Enables BPDU Gurad on all portfast interfaces
 `spanning-tree bpdguard enable` | Enbales BPDU Gurad 
 `spanning-tree mode` *mode* | Configures  STP mode
 `spanning-tree vlan <vlan number> root primary` | Configures the root bridge
 `spanning-tree vlan <vlan number> root secondary` | Configures the secondary root bridge
 `show spanning-tree` | Displays global information for STP

# CDP Configuration Commands 
| Command  | Purpose | 
|:----------:|:-------------:|
 `cdp run` | Enables cdp 
 `cdp enable` | Enables cdp
 `show cdp` | Displays global information for CDPDisplays global information for LLDP
 `show cdp neighbors` |  Displays all CDP neighbors

# LLDP Configuration Commands 
| Command  | Purpose | 
 |:----------:|:-------------:|
 `lldp run` | Enables LLDP 
 `show lldp` | Displays global information for LLDP
 `show lldp neighbors` | Displays the list of LLDP neighbors
 `show lldp neighbors detail` | Displays more details from the list of LLDP neighbors

 
# Clock & NTP Configuration Commands 
| Command  | Purpose | 
|:----------:|:-------------:|
 `clock set hh:mm:ss {day/month} {month/day} year` | Manually configure the software clock 
 `calendar set hh:mm:ss {day/month} {month/day} year` | Manually configure the hardware clock 
 `clock timezone  <name of time zone> [minuits-offest]` | Configures the timezone 
 `clock update calendar` | Synchronizes the hardware to the software's time 
 `clock read calender` | Synchronizes the software to the calender's time
 `clock summer-time reccuring <name> <start> <end> [offest]` | Automatically configure summer time
 `ntp server <IP>` | Configures ntp server
 `ntp master` [number] | Manually configure an device to act like an ntp sever
 `ntp peer <IP address>` | Symmetric active mode 
 `ntp authenticate` | Enable NTP authentication
 `ntp authentication-key <key number> md5 <key>` | Create the authentication key(s)
 `ntp trusted-key <key-number>` | Specified which key(s) is trusted
 `ip nat` *inside / outside* | It designate whether the interface is the inside or outside of NAT
 `show clock` | View the time 
 `show clock detail` | View the time source of the device 
 `show calendar` | View the calendar 
 `show ntp status` | View the ntp status
 `show ntp associations` | View all the servers you configured 


# DNS  Configuration Commands 
### Windows Commads
| Command  | Purpose | 
|:----------:|:-------------:|
`ipconfig /displaydns` | View the DNS cache
`ipconfig /flushdns` | Clears the DNS cache 
### IOS Commands
| Command  | Purpose | 
|:----------:|:-------------:|
`ip dns server` | Configures a router as a DNS server 
`ip host <host> <IP address>` | Configures a list of mappings 
`ip name-server <IP address>` | Configures an external DNS server
`ip domain-name` *name* | Conﬁgures a DNS domain name 
`ip domain lookup` | Enables DNS lookup
`show hosts` | Disables the configured and learned hosts 
 

 # DHCP Configuration Commands
 ### Windows Commads
 | Command  | Purpose | 
|:----------:|:-------------:|
 `ipconfig /release` | Releases the DHCP learned IP address
 `ipconfig /renew` | Gets an IP address from a DHCP server
 
 ### IOS Commands
  | Command  | Purpose | 
|:----------:|:-------------:|
`ip dhcp excluded-address <low-address> <high-address>` | Specifies IP addresses that a DHCP server should not assign to DHCP clients
`ip dhcp pool` *name* | Creates a DHCP pool / Entres DHCP config mode
`network <network-number> <mask>` | Configures the network number and mask for a DHCP address pool 
`default-router <address>` | Specifies the default router list for a DHCP client
 `lease` *days* *hours* *minuts*| Configures the lease time 
 `lease infinit` | 
 `show dhcp biding` | Displays all of the DHCP clients
 `ip helper-address` *address* | Configure a DHCP relay-agent
 `ip address dhcp` | Configures a DHCP client 
