# Cisco CCENT/CCNA ICND1 100-105

## What is Network Administration and Engineering

## OSI layers

### Why

1. Clean and Crisp
2. High risk/ (high reward)
3. Adventure

* Routing and Switching
* Security
* Collaboration
* Design
* Wireless

## Understanding the Cisco Certification Program

* multiple areas of expertise with varied focus
  * ICND1 -> CCENT
  * ICEND2 -> CCNA
  * CCNP
* Each Experience level comprised of one or more exams
* Each exam has a 3-year shelf life
  * Exam renewal policy
  * certification Growth

### Most Popular Paths

1. Routing and Switching
* Security
* Wireless
* Collaboration

### College degree vs. certification

* Education = value
* College =  General studies, some specialization, keep it forever
* Certification =  targeted, direct training, always updating
* And the winner is?
  * Certifications

### Cisco Certification FAQ

* ICND1 vs Composite
* what can I talk about on exam?
  * Non-disclosure Agreement
* Do I need experience for CCNP
  * No, but having practical experience wouldn't hurt

## Cisco Lab: Critical Pieces

* Cisco Switch
* Cisco Router

### Mission not Memorization

* GNS3 is a network emulator for Cisco
* packet tracer is a network simulator for Cisco
* In ICND1 and ICND2... Use neither. Mostly.

## Network Fundamentals

### Network Switch

* MDF `Main Data Frame`

* Hub -> Bridge -> Switch

* __Application Specific Integrated Circuitry__

Layer 2 Switch

* can read mac addresses

Layer 3 Switch

* Has routing capabilities

### Network Routers

* Contains networks
* Moves data between networks
* Connects dissimilar networks
* Software-based, feature rich

* **IOS**

* Internetwork Operating System

### Network WAP and Controller

* Wireless Access Point Translates wired into airwaves
* A whole new world of managing the unmanageable
* 2.4 GHz or 5 GHz Spectrums
  * lower the frequency, longer range, lower bandwidth
  * higher the frequency, smaller range, higher bandwidth
  * 2.4 has issues with lots of
* Controlling the minions
  * Helps mange larger amounts of WAPs
  * can auto adopt new APs and auto configure them

### Network Firewall / IPS

* Block or allow traffic from moving between networks
  * let the firewall be the firewall, and the router be the Router
  * Router allows everything, and denies by exception
  * Firewall denies everything, and allows by exception
* Transparent or routed
  * Transparent mode allows them to be run without being seen
  * routed divided up the networks
* Allow/deny paradigm shift... Key word: "Stateful"
  * firewall will let the internet in. but only by exception
* Integrated or separate intrusion prevention system (IPS)
  * Watches for abnormalities.

## The difference between bits and bytes

* Difference between storage and networks
  * Computers deal in bytes, networks deal in bits
* Networks can't actually send a byte of data
* Storage reaches into the tera / penta realm
* Networks reaches into the giga realm

* __Mbps__
* __Gbps__

* Internet and Wan always a bottleneck
* Computers = 100m, 1G
* 1G, 10G, 40G (EC)
  * EC - ether channel
  * can bundle up to 8 channels
* inter-switch link = 1G, 10G, 40G (EC)
  * CSMA/CD - Carrier Sense Multiple Access  Collision Detection
* Routers = 100m, 1G, 10G ()
* WAP
  * CSMA/CA Carrier Sense Multiple Access Collision Avoidance
  * TR uses old token ring technology
  * 5mbps - 60mbps

Bits and bytes
Kilo, Mega, Giga, and beyond

## Network Cabling

### Ethernet

* MDF
  * Main Distribution Facility
* IDF
  * Intermediary Distribution Facility
* DMARC
  * ISP responsibility to fix.
  * Could be Ethernet, Fiber Optic, and Serial...the Grandfather

Ethernet | Multimode Fiber| Single Mode Fiber
:---: | :---: | :---:
100 meters | 500 meters | 2-50 miles

Types | Meaning
:---:| :---:
UTP | Unshielded Twisted Pair
STP | Shielded twisted Pair

568 A | Pin | 568 B
:--- | :---: | :---
white/green | 1 | white/orange
green | 2 | orange
white/orange | 3 | white/green
blue | 4 | blue
white/blue | 5 | white/blue
green | 6 | green
white/brown | 7 | white/brown
brown | 8 | brown

Straight | Crossover | Rollover
:---: | :---: | :---:
Connects unlike devices | Connects like devices | Rolls the pins over
 Both ends the same| 568 A --- 568 B | 1-8, 2-7, ...

Auto MDIX can tell what the device is on the other side, and doing away with straight and crossover.

### Stars, Meshes, Hybrid

* Difference ways things are connected to one another.
* x-25
* FR
* ATM
* MPLS

### Spanning Tree Protocol STP

* Puts a stop to redundancy connection until its needed.

#### Star

* Very cost effective

#### Mesh

* Provides a large amount of redundancy

## IP Communication Types

* CCNA Collaboration is about Video and VoIP
* CUCM Publisher
* CUCM Subscriber
* Cisco Unity
* AD/DNS Server

* Unicast: One to one
  * provides music to each person on hold.
  * __ can go past the router __
* Multicast: One to many
  * Music on hold is always on
  * Video casting
    * __ can go past the router __
* Broadcast: One to all
  * DHCP
  * Provides an IP address to the phone
  * ARP Address Resolution Protocol
  * Short, sweet, over
* Anycast: One to closest
  * IPv6
  * Finds the closest server to you with the address you're looking for.
  * IPv4 uses DNS to do this.

## Defining a Network

### Defining the Network Neighborhood

* The network allows our computers to talk
  * the network allows Communication
* IP
  * the router provides boundaries
  * These boundaries provide different groupings
  * Without these boundaries, everything becomes mush.
* The network boundary - mask defined
* the first three octets represent the network
* Subnet purpose is to define the size of the network boundary
  * Where you see a 255 that represents a networks
  * Where you see a 0 that represents the host
* Devices that are grouped together that have the same network identifier as defined by the subnet mask.
* Class C Subnet
  * 255.255.255.0
  * gives you 254 host
* Class B subnet
  * 255.255.0.0
  * gives you 65,534 host
* Class A Subnet
  * 255.0.0.0
  * 16,777,214
* Smart Computers can reach other computers on that networks
  * the GW is what allows us to leave the internal network.
  * can decide which set of IPs it needs to access what it's trying to get too.
  * there is a need for 2 addresses

### Public and Private Addressing

#### Private IPv4 Address Ranges

RFC1918 name | IP address range | number of addresses
--- | --- |---
24-bit block | 10.0.0.0 - 10.255.255.255 | 16,777,216
20-bit block | 172.16.0.0 - 172.31.255.255 | 1,048,576
16-bit block | 192.168.0.0 - 192.168.255.255 | 65,536
RFC - `Request for Comments Standard`

`Addresses inside of these private addresses won't be able to route on the internet`

`Every internet service provider they should put a firewall rule in place that prevents people with these addresses from getting out on the internet, because they are non-regulated IP addresses.`

### NAT

#### Network Address translation

* Translate private IP addresses to Public ones
* All private IPs assume the same Public IP
* Prohibiter of Innovation

## Gluing IP devices together

### DNS

* sends a get message, and assembles a packet
* get source IP header
* get destination IP header
* get source mac
* get destination Mac

__ the need for two addresses __

* MAC addresses
  * `Media Address Control`

### ARP

`Address Resolution Protocol`

* Sends out a broadcast message to the network to determine who is the IP address
* The switch looks at the MAC Addresses
* Switch will add the MAC to its CAM table

* Source IP is my IP
* Destination IP is where I'm wanting to go
* Source MAC is me
* Destination MAC is the default gateway

* Once it passes the network, the Source and Destination MAC address is ripped off

__ The front and end IP addresses stay the same.  __

## Selecting your Protocol

* __TCP__ `Transmission Control Protocol`
  * reliable network Communication
  * __3 way hand shake__
  * Session relationship
    * first: TCP SYN `Synchronization Message`
      * sends sequence number
    * SYN/ACK
    * ACK
  * This information is used until the connection is terminated

* __TCP Sliding Windows__
* It starts out by sending small amounts of data to test the connection and then continues to increase till something on the chain maxes out
* __UD__ `User datagram protocol`
  * unreliable network Communication
  * send in hope it gets there
* __ICMP__ `Internet Control Message Protocol`
  * Developed for controlled messages
  * `PING`
  * sends echo, and gets an echo reply

## Completing the End-to-end story

* __Wireshark is awesome__

## Tools you can't live Without

* __PING__
  * checks connections between Devices
  * ICMP Protocol

* __ARP__
  * tells you what IP is associated with what MAC address
  * arp -a to see the cache
  * arp -d * clears the cache

* __Telnet__
  * Management
  * Uses clear text to connected device
  * Check to see if ports are Open

* __PuTTy__
  * SSH
  * SecureCRT

__ipconfig/ifconfig__
__nslookup__

## Three Tier Architecture

* Core
  * Not necessary until you have multiple locations
  * Center point of cross connect
* Distribution layer
  * Routing
  * QOS
  * various over things as well
* Access layer Switch
  * `More of a framework and not like connections going everywhere`

## OSI Model

`where its at`

### What is the OSI Model

* A Standard Architecture defining network Communication
* A system to "Break Down" network Communication
  * You approach repair in a layers without thinking about it.
* A standard to create standards
  * People can create equipment to work at a particular layer and below.
* a competing protocol to TCP/IP
  * OSI was created as a competing protocol, however TCP won.
  * OSI was better, TCP was simpler

Layer | |What it does
:---: | :---: | ---
7 | `Application` | Where the network aware application resides (i.e. the web browser)
6 | `Presentation` | where the generic standards reside, uses generic encryption (i.e. html, jpeg, etc.)
5 | `Session` | Starts and ends the session between the server
4 | Transport | This layer has two major function, pick your protocol `(TCP/UDP)*` and pick your port `show it knows where to put the information`.
3 | Network | IP address End-to-end address, where it came from, where it's going `routing`
2 | Datalink | Adds the MAC address, Hop-to-hop `Switching`
1 | Physical | The cable that is in use

`The Computer - these layers are not a network engineers problem`

`* TCP reliability, UDP Speed`

This whole process is known as encapsulation.

## TCP/IP Model

### DOD Model

Layer | Description | OSI reference
--- | --- | :---:
4 | Application | OSI 5-7
3 | Transport | OSI 4
2 | Internet | OSI 3
1 | Network Access | OSI 1-2

__ About as useful as giving a snow cone to an Eskimo. __

## Encapsulation, frame Format, and Wireshark

2 |  GET   | 4 | 3 | 3 | 2 |2 |
:---: | :---: | --- | --- | --- | --- | --- | ---
FCS `Frame Check Sequence` | DATA | TCP/UDP Ports | SRC IP | DST IP | SRC MAC | DST MAC

### TCP Header

![alt text][TCP header Format]

[TCP header Format]: https://nmap.org/book/images/hdr/MJB-TCP-Header-800x564.png

`DNS lookups UDP Port 53`

## IOS Fundamentals

### Defining the purpose of IOS

* Command-Line, Context-sensitive operating system to control Cisco Devices
  * `#` this mode is used to show commands
  * `(config)#` used to configure the device
* Monolithic and Modular designs, major and minor versions
  * You get the base platform, and then choose ad on modules
* Platform Specific, memory requirements
* Understanding SmartNet
  * Support and Version upgrade contract

### Command Line Benefits

* Impress your friends, look Smart
* Troubleshooting and diagnostics far beyond GUI
* Tuning and tweaking configurations far beyond GUY
* Remote Accessibility, OS / Browser independence
* Configuration speed, script ability, automation

## How do I get to the IOS

* Console Ports
* Telnet
* SSH

### Context Sensitive Help and Keyboard Shortcuts

* ?
  * shows you all commands for that specific mode
* enable
* configuration Terminal
  * logging synchronous
* ctrl + z
  * drops you back to privileged mode

### File System

* Inside the Device
  * RAM
    * Fast memory/volatile
  * NVRAM
    * Non Volatile
  * FLASH
    * Slow storage medium

    `Reload in` reboot the device just in case you lose connection

    `reload cancel` removes re

    copy running-config startup config  `Need for Exam`

    wr mem `Fastest Save`

    wr erase `deletes the config`

    configure replace

* Outside the Device
  * TFTP server
  * HTTP Server
  * Other

### Best Base Configuration Ever

* no ip domain-lookup
* service password-encryption

* Hostname
* Banner
* Logging synchronous
* Console password
* VTY (telnet) password
* IP address / activate interface
* No IP domain-lookup
* Service password encryption
* Enable password / secret
* copy run start

### Preparing a Device for remote management

* Clear config
  * wr erase (old)
  * erase startup-config
  * switches only delete flash:vlan.dat
* Assigning IP Addresses, passwords
* testing via ping and telnet

### Establishing SSH on Cisco Device

* Create a domain name
  * FQDN ip domain
  * ip domain-name
* line vty
  * transport input ssh
  * password
  * login local `use the local user database`
* crypto key generate rsa
* username ___ secret
* sh users
  * clear line vty ___

### Understanding Interface Syntax

* Unveiling "THE" Command
  * sh ip int brief
  * Physical Layer of OSI
    * Up
    * Down
    * Administratively down
* Understanding Cisco Interface Syntax
  * General
    * type
    * blade/module/port

## Switching Fundamentals

### Cisco Three Tier Hierarchy

![alt text][Cisco Three Tier Hierarchy]

[Cisco Three Tier Hierarchy]: http://study-ccna.com/wp-content/uploads/2016/02/cisco_hierarchical_model.jpg

* Learn and Store mac-addresses in CAM and route remembers that for 5 minutes if unless its talking)
* Mac addresses flooded out all ports except the one it was received on
* Application Specific IIntegrated Circuitry (ASIC) Powered

Layer 2 - Frame
Layer 3 - Packet

* Carrier sense multiple access collision detection
  * CSMA/CD
  * CSMA/CA Wireless

### Finding Network Devices

* ping the IP
* arp -a
  * show the device mac address
* sh mac address-table | include `last 4 of mac`
* sh mac address table int
  * make sure there isn't other devices connected to where you're looking
* sh cdp neighbors
* conf t
  * int `port number`
  * shutdown
* POE
  * Wireless
  * Phones
  * Cameras

### Configuring the Switch Management IP Address

#### Switch 1 & 2 Base Config

* en
* conf t
* hostname sw1
* ip domain-name ryanngay.com
* crypto key gen rsa
  * name `sw1.ryanngay.com`
  * 1024
* username ryan secret cisco
* line console 0
  * logging sync
  * no exec-time
  * exit
* line vty 0 4
  * login local
  * exec-timeout 60
  * transport input telnet ssh
  * exit
* no ip domain-lookup
* enable secret cisco
* exit
* int VLAN 1
  * no shutdown
  * `switch 1` ip address 10.1.1.2
  * `switch 2` ip address 10.1.1.3

#### Router Base Config

* en
* conf t
* hostname sw1
* ip domain-name ryanngay.com
* crypto key gen rsa
  * name `sw1.ryanngay.com`
  * 1024
* username ryan secret cisco
* line console 0
  * logging sync
  * no exec-time
  * exit
* line vty 0 4
  * login local
  * exec-timeout 60
  * transport input telnet ssh
  * exit
* no ip domain-lookup
* enable secret cisco
* exit
* int G0/0
  * ip address 10.1.1.1/24

## Speed and Duplex

* Network Speed Has Increased over Time
  * Ethernet= 10MBPS
  * Fast Ethernet= 100 MBPS `SPECIAL`
    * Auto `try to negotiate with the other side`
    * Didn't work quite right every time
    * when it doesn't work, one side will send and receive at the same time, the other side will only do one or the other.
    * The `Network Seems Slow`
  * Gigabit Ethernet= 1000 MBPS
    * Use Auto unless connected to a fast Ethernet, then hard code it
  * ...and Beyond
* And standards have changed...
  * Half Duplex
  * Full Duplex

### Hard code the interface

* On Key Fast Ethernet Devices, best practice recommends running these commands.
  * conf t
    * in fa -/-/-
    * speed 100
    * duplex full

## Switching Day to day

### Understanding Port Security

* The Purpose and Place of Port Security
  * We Care about things plugging into our network
    * We want to know when someone plugs something in
    * BYOD can cause your network to go down
  * Two types of security:
    1. (Everyone) Limit the number of mac addresses on each port
    2. (Security Centric) Limit what mac addresses can access the port
       * Statically configured
       * Sticky mac address
  * Three response types:
    * Protect
      * If limited to 1 mac address, and a second devices is plugged in, then the second device won't work.
    * Restrict
      * If limited to 1 mac address, and a second devices is plugged in, then the second device won't work. It will log the port security violation.
    * and Shutdown
      * Default State
* Implementing basic port security
  * Switch 1 Port Security Config
    * int range -/-/-
      * switchport mode access
      * switchport port-security maximum 1
      * do sh run int _-/-/
    * sh int port-security int _-/-/-
    * conf t
      * int _-/-/-
        * shutdown
        * no shutdown
        * switchport port-security
        * switchport port-security mac-address sticky
    * Re-enable a Port
      * shutdown
      * no shut
* Implementing Mac Address restrictions

### Handling "The Network is slow"

* How to tell is the network is slow `speedtest consistency, iperf`
  1. SpeedTest sites
     * <https://speedtest.net>
     * <https://speakeasy.net/speedtest>
     * <https://speedof.me>
  2. Watch speed and consistency of speed
  3. Internal testing - IPerf `client/server`
  4. Wired vs wireless - Never accept only a wireless test
  5. Know your baseline usage and bandwidth capacity
* Key interface counters
  * Trace the switchport path between source and destination
  * Use the `show interface` command to review statistics
    * `tx` send
    * `rx` receive
    * `runts` packet smaller than what's expected, it can be dropped
    * `giant` bigger than a packet should be, it will be dropped
  * Key "Performance" counters:
    * Duplex/Speed
    * 5 minutes output rates
    * Input errors
      * Some kind of cabling issue or bad interface
    * `CRC` Cyclical Redundancy check
      * `FCS` Frame Check Sequence
      * checks to make sure its valid
      * bad cable, bad interface, layer 1 issue
    * collision
      * Own collision domain
        * collision devices try to send when its not supposed too. Usually happens in a duplex mismatch
        * Causes major network issues
    * late collisions
      * Happens when a collision happens later than it should. CSMA/CD
      * Happens if its past the 32 bits of the frame
      * If the cable is to long, or if there are to many devices in between
    * interface resets
      * This will happen if to many errors build up in an attempt to reset the interface

## Switching VLANs

### The Concept that Changed the Networking World

* Understanding the Problem
  * There is virtually no security at Layer 2
  * There is no segmentation at layer 2
    * Led to the network slowing down drastically
  * There is no real way to differentiate devices at layer 2

#### QOS Recommendations

Service Type | Bandwidth Allocated
:---: | :---:
Voice | 33%
Mission Critical Data | 35%
Voice Signaling | 7%
Everything else | 25%

* Old School Solution
  1. Routers Everywhere
     * Every interface of a router is a subnet, it introduces a subnet
     * ACL Access Control List
     * Routers stop broadcasts
     * Routers are slow, causing them to be a bottle neck on the network
     * physical limitations
  2. Servers on Every Network

* The VLAN Solution `Virtual Local Area Network`
* VLANS segment the network on a per-port basis
  * VLANs create multiple broadcast domains/subnets/networks
    * Broadcasts will stay within the same VLAN
  * VLANs Extend the entire Layer 2 fabric (stop at router)
    * VLANs can be access across multiple switches
    * Trunks carry all VLANs across the switches
  * VLANs segment and isolate traffic

### Routing between VLANs

* Using a router
  * THe Old, but valid Possibility
  * Drawback
    * Limited number of Router Interfaces

* The Router on a Stick (ROAS)
  * Trunk Port
  * Sub interfaces
    * Allows us to take 1 interface, and split it into multiple interfaces
    * The Cloud, a bunch of data centers, ROAS

* Using a Layer 3 Switch
  * Combines the best of Routing and Switching, and puts them into one device.
  * Not a Frankenstein Device
  * Layer 3 Switching takes the core of Routing, and makes it ASIC `Application Specific Intergrated Circuitry` Based

### Trunking VLANS to other Switches

* Tagging Done Between Switches with 802.1q protocol
  * Industry Standard
  * ISL `Inner Switch Link`
* Tag removed on exiting `access port`
  * `Access Port` any non trunked interface
  * These devices access only one VLAN
* Trunk ports configured on each interface
  * If you aren't careful about which ports you trunk, and a user is plugged into a trunk port, they can do a VLAN Hopping Attack

* How the Dynamic Trunking Protocol Works
  * When a switch is plugged in, it builds trunk
  * When a computer is plugged in, it builds an access port
  * Enable Trunk Ports
    * Manual Configuration (Trunk/nonegotiate)
    * ~~Dynamic Configuration (Dynamic Auto/Dynamic Desirable)~~
  * Dynamic Configuration can be Creepy; Use Nonegotiate

* Trunk ports should receive traffic with tags
* but what is it doesn't? `Native VLAN`
  * Native VLAN is for when it receives traffic that doesn't have a tag attached to it
  * CDP
* But how?
  * Switchport Originated Traffic
  * Pass-through Device
  * Virtualized Servers

### The Weird and Scary World of VTP

* What is VTP
  * Conforms your network
  * Allows you to add a VLAN to 1 switch, and will replicate it to your other switches
  * Cisco Recommends you not use it
  * VTP REV #0
  * VTP Domain
  * Can take down the entire network
  * To fix the network down issues, you need to re-add the VLAN to change the VLAN Database
    * Client `Can't make changes to the databases`
    * Server `This is default`
    * Transparent `will turn this off`
  * Enabled by default, as soon as its plugged in, it will form the trunk, it will join the domain
  * Nightmare from a Security Perspective

### Configuring and Testing VLANs

```switch
Switch

conf t
  vlan 2
    name ACCT
    exit
  vlan 3
    name SALES
    exit
  int range _-/-/_-_
    switchport mode access
    switchport access vlan 2
    exit
  int range _-/-/_-_
    switchport mode access
    switchport access vlan 3
    exit
  int range _-/-/_-_
    spanning-tree portfast
```

When in **Configuration Mode** use the `do` command to drop down to privilege mode.

## Switch Troubleshooting

### Where to Look

* Scenario 1: Student Testing is not working
  * Classroom 1 seems to be broken, the other 4 classes are fine
  * `sh int status`
  * syslog
* Scenario 2: Accounting spreadsheets are an bearable
  * `clear counters int _-/-/-`
* Scenario 3: Public WiFi is down
  * `switchport trunk allowed vlan add _`
  * if you do not use add, you will remove the other VLANs
