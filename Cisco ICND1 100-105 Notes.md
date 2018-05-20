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

#### Network Address translation Description

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

## Routing Fundamentals

### How Routing Works

* Revisiting the Essence of IP Communication
  * The Network Boundary - Mask Defined
  * Smart Computers
  * The Need for Two Addresses
  * DNS and NAT
  * Public and Private
  * ARP
* Configuring some Interfaces
* Exploring the Routing Table

```text
Router Config

Line Console 0
  logging Synch
  no exec timeout
Line vty 0 4
  login
  password cisco
  enable secret cisco
int _-/-
  ip address 172.30.100.1 255.255.255.0
  no shutdown
int _-/-
  no shutdown
  ip address [Whatever info the ISP provides you with]

ip route 0.0.0.0 0.0.0.0 [Whatever info the ISP provides you with]
```

**THE COMMAND** to know on routers `sh ip route`

### Using Static Routing

* Static Routing...Defined
* Static Routing Usage Scenarios
* Static Routing Configuration

```text
Router 1
conf t
  hostname R1
  line console 0
    logging synchonous
    no exec-timeout
    exit
  int s0/0/0
    ip address 10.5.2.1 255.255.255.0
    no shutdown
    clock rate 64000
    exit
  int g0/0
    no shutdown
    ip address 10.5.1.1 255.255.255.0
    exit
  ip route 10.5.3.0 255.255.255.0 10.5.2.2

  int g0/1
    no shutdown
    ip address 10.5.4.1 255.255.255.0
    exit

    ip route 10.5.3.0 255.255.255.0 10.5.4.2 10

Router 2
conf t
  hostname R2
  line console 0
    logging synchonous
    no exec-timeout
    exit
  int s0/0/0
    ip address 10.5.2.2 255.255.255.0
    no shutdown
    exit
  int g0/0
    no shutdown
    ip address 10.5.3.1 255.255.255.0
    exit
  ip route 10.5.1.0 255.255.255.0 10.5.2.1

  int g0/1
    no shutdown
    ip address 10.5.4.2 255.255.255.0
    exit

  ip route 10.5.1.0 255.255.255.0 10.5.4.1 10

  ip route 0.0.0.0 0.0.0.0 10.5.4.1 [Gateway of last resort]
```

``` text
Things to note

Serial Connnectors
  sh controllers s-/-
  Can tell which side is connected
  DCE v.35

  clock rate ?

Floating Static Route
  ip route A.B.C.D e.f.g.h i.j.k.l -Distance-

The Rule of Specitifity
  When Routing, going to prefer the most specific router
```

### Routing Between VLANs

```text
Switch
  conf t
    vlan 51
      name ENG
      ip address 10.1.51.1 255.255.255.0
      exit
    vlan 52
      name MGMT
      ip address 10.1.52.1 255.255.255.0
      exit
    int g1/0/1
      switchport mode access
      switchport access vlan 51
      exit
    int g1/0/2
      switchport mode access
      switchport access vlan 52
      exit
    int g1/0/24
      switchport trunk encapsilation dot1q
      switchport mode trunk
      switchport nonegotiate


Router
  conf t
    int g0/0.51
      encapsulation dot1q 51
      ip address 10.1.51.1 255.255.255.0
      exit
    int g0/0.52
      encapsulation dot1q 52
      ip address 10.1.52.1 255.255.255.0
      exit
```

### Layer 3 Switching

```text
Switch Config
conf t
  vlan 51
    name ENG
    exit
  vlan 52
    name MGMT
    exit
  int g1/0/2
    switchport mode access
    switchport access vlan 51
    exit
  int g1/0/3
    switchport mode access
    switchport access vlan 52
    exit
  ip routing
  int vlan 51
    ip add 10.1.51.1 255.255.255.0
    exit
  int vlan 51
    ip add 10.1.51.1 255.255.255.0
    exit
```

**SVI** `Switch Virtual Interface`

### DHCP in a Routed World

* Understanding DHCP, Client Requests, DHCP Options
  * Broadcast-based, Central IP distribution
    * **Broadcast** the router will stop it
  * Minimal Client Interaction
  * Assigns IP address and DHCP options
    * Option 1: Subnet Mask
    * Option 3: Router (Gateway)
    * Option 6: DNS Server(s)
    * ...and hundreds of others
  * Clients usually prefer the same IP
* How DHCP is Usually Handled
  * DHCP from a network device (same network)
  * DHCP relay from a central DHCP server
  * **DHCP is a critical service**
* Understanding DHCP Replay
  * configure the interface to DHCP relay at the ip address of that server
  * router converts the DCHP broadcast request, and sends it to the server as a Unicast

### Configuring DHCP

```text
Router Server Based

  Switch Conf
    conf t
      hostname S1
      vlan 51
        name ENG
        exit
      vlan 52
        name MGMT
        exit
      int g1/0/2
        switchport mode access
        switchport access vlan 51
        exit
      int g1/0/3
        switchport mode access
        switchport access vlan 52
        exit
      int g1/0/1
        switchport mode trunk
        switchport trunk allowed vlans 51,52
        exit

  Router Conf
    conf t
      int g0/0
        no shut
        exit
      int g0/0.51
        encapsulation dot1q 51
        ip address 10.1.51.1 255.255.255.0
        exit
      int g0/0.52
        encapsulation dot1q 52
        ip address 10.1.52.1 255.255.255.0
        exit
      ip dhcp excluded-address 10.1.51.1 10.1.51.19
      ip dhcp excluded-address 10.1.51.100 10.1.51.255
      ip dhcp pool VLAN51
        network 10.1.51.0 /24
        default-router 10.1.51.1
        dns-server 4.2.2.2 8.8.8.8
        exit
      ip dhcp excluded-address 10.1.52.1 10.1.52.19
      ip dhcp excluded-address 10.1.52.100 10.1.52.255
      ip dhcp pool VLAN52
        network 10.1.52.0 /24
        default-router 10.1.52.1
        dns-server 4.2.2.2 8.8.8.8
        exit

  Router with no dhcp
    conf t
      no ip dhcp excluded-address 10.1.51.1 10.1.51.19
      no ip dhcp excluded-address 10.1.51.100 10.1.51.255
      no ip dhcp pool VLAN51
      no ip dhcp excluded-address 10.1.52.1 10.1.52.19
      no ip dhcp excluded-address 10.1.52.100 10.1.52.255
      no ip dhcp pool VLAN52
      int g0/0.52
        ip helper-address 10.1.51.200


```

#### Useful Commands from this Nugget

* **sh ip dhcp binding**
* **sh run | section ___**
* ipconfig /release `releases the IP back to the DHCP pool`
* ipconfig /renew `asks for a new address`

### What are Routing Protocols

* What is a Routing Protocol
  * A Router knows about **ONE** type of network by default
  * Routing Protocol: Educate a router without your involvement
    * RIP
    * BGP
    * EIGRP
    * ...many more
  * Routing Protocols are dynamic, forming neighbors, detecting failures
    * They use the **Hello** Protocol
* Distance Vector Attributes
  * Only Knows what the neighbor tells it
  * Memory / Processor Efficient
  * Loop Prevention Mechanisms Needed
    * RIP
    * EIGRP
    * BGP
* Link State Attributes
  * Maintains a map of the network system
  * Resource Consuming
  * Maintains Loop free by nature
    * OSPF
    * IS-IS

### Pick your flavor

`ICND 1, only need to know RIP`

* Yes... RIP is important (again)
  * Created in 1988 (v1)
    * broadcast based broadcast to share your routing table
  * 1993 (v2)
    * Made it to a multicast based protocol that would only send their information to other routers using RIP
    * Its achilleas heal was its **Metric** How does the routing protocol find the best way around the network.
    * **Metric** Uses Hop count
    * Would send the entire routing table with every hello
* IGRP
  * Uses bandwidth and delay on the links, That would be its Metric
  * Was meant to compete with RIP, Cisco Proprietary.
  * Took long to discontent
  * Would send the entire routing table with every hello
* EIGRP
  * Was Proprietary, but later released as an RFC open standard.
  * Talks the bandwidth and delay aspect of IGRP, and is lightning fast.
  * do an initial exchange, after that, now all it does is says hello
  * sub-second convergence
  * un-equal cost load balancing
* OSPF
  * Almost all the benefits of EIGRP
  * Most Popular, born to be an Standard
  * based off of bandwidth alone
  * uses a link state database
* IS-IS
  * back in the day there was TCP/IP and OSI
  * OSI Protocol created IS-IS
  * Internet Service Provider Networks only
  * Integrated IS-IS

* sh ip route
  * Shows only the best of the best in the routing table

### Understanding RIPv2

* Why v2? What happened to v1?
  * v1
    * Broadcast based protocol
    * one to all
    * could be a security vulnerably
  * v2
  * Multicast based protocol
  * one to a group
  * moves from a classful, to classless
* Tell your life in 30 seconds
* It's time to be a little classless...
  * class a 0-127 (255.0.0.0)
  * class b 128-191 (255.255.0.0)
  * class c 192-223 (255.255.255.0)
* Where does this protocol fit? Anywhere
  * slowest protocol
  * implement, monitor, troubleshoot a routing protocol
  * commands to know
    * `router rip`
    * `version 2`
    * `network`
      * tells rip what networks to advertise
      * tells rip what interfaces to send advertisements out of

### Configuring RIPv2

```text
Router 1
  conf t
    int g0/0
      no shutdown
      ip address 10.5.1.1 255.255.255.0
      exit
    int s0/0/0
      no shutdown
      clock rate 64000
      ip address 10.5.2.1 255.255.255.0
      exit
    router rip
      version 2
      network 10.0.0.0
      end
  sh ip route

  conf t
    int g0/1
      no shutdown
      ip address 192.168.1.1 255.255.255.0
      exit
    router rip
      network 192.168.1.0
      no auto-summary
      end

Router 2
  conf t
    int g0/0
      no shutdown
      ip address 10.5.3.1 255.255.255.0
      exit
    int s0/0/0
      no shutdown
      clock rate 64000
      ip address 10.5.2.2 255.255.255.0
      exit
    router rip
      version 2
      network 10.0.0.0
      end
  sh ip route

  conf t
    int g0/1
      no shutdown
      ip address 192.168.1.2 255.255.255.0
      exit
    router rip
      network 192.168.1.0
      end


Computer 1
  ip address 10.5.1.50
  net mask 255.255.255.0
  gateway 10.5.1.1

Computer 2
  ip address 10.5.3.50
  net mask 255.255.255.0
  gateway is 10.5.3.1
```

* [Administrative Distance / Metric]
* `Adminstrative Distance` the lower the number, the more believable it is
* `Metric` it can get to the over network via hops, the lower the better
* Auto Summary

## IPv4 Subnetting

### Why are We Doing This

* Classful vs Classless World
  * IPv4 Address:
    * Example: 10.10.10.1
    * Four Octet (byte) Address
    * Can be one of three different classes
    * When combined with a subnet mask, defines a network and host portion
    * operates at Layer 3 of the OSI Model
    * Works closely with layer 2 address (hop-by-hop)
* The Need for Smaller and Bigger Chunks
  * Class A Private Range: Anything starting with 10
    * Example: 10.0.0.0 - 10.255.255.255/8
  * Class B Private Range: Anything Starting with 172.16
    * Example: 172.16.0.0 - 172.31.255.255/16
  * Class C Private Range: Anything Starting with 162.168
    * Example: 192.168.0.0 -192.168.255.255
  * We can define different entities of hosts as we customize each network
* What's it take?

### Binary Conversion

* THe world according to Rico
  * and his new light weight brink illustration
* Binary Conversion Exercises

### Subnetting Based on Network Requirements

1. Scenario 1:
    * This organization has purchased the Class C Address 216.21.5.0 and s would like to use it to address this network.
      * RFC1918
      * Determine Number of Networks and Convert it to Binary: 5 = 00000101
      * Reserve Bits in subnet, and find your increment
        * 255.255.255.0
        * 11111111.11111111.11111111.00000000
        * host bits 11100000
        * increment 32
        * subnet:255.255.255.224
        * CIDR /27
      * Use increment to find your network ranges
        * 216.21.5.0-216.21.5.31
        * 216.21.5.32-216.21.5.63
        * 216.21.5.64-216.21.5.95
        * 216.21.5.96-216.21.5.127
        * 8 total networks
2. Scenario 2:
    1. Determine number of networks and convert to Binary
        1. Class C: 195.5.20.0
        2. Need 50 networks
        3. 00110010
    2. Reserve Bits in subnet mask and find your increment
        1. 255.255.255.0
        2. 1111111.11111111.11111111.00000000
        3. 111111
        4. 255.255.255.252
        5. CIDR /30
    3. Use increment to find your network range
        1. 95.5.20.0-195.5.20.3
        2. 195.5.20.4-195.5.20.7
        3. 195.5.20.8-195.5.20.11
        4. 195.5.20.12-195.5.20.15
        5. 195.5.20.16-195.5.20.19
        6. ...
        7. Total of 64 networks
        8. Second most popular Subnet in the world
        9. Excellent for Point-to-point connections
3. Scenario 3:
    1. Determine number of networks and convert to Binary
        1. Class B: 150.5.0.0
        2. Need 100 Networks
        3. 01100100
        4. 100 = 7 bits
    2. Reserve Bits in subnet mask and find your increment
        1. 255.255.0.0
        2. 11111111.11111111.00000000.00000000
        3. subnet: 255.255.254.0
        4. increment 2
        5. CIDR /23
    3. Use increment to find your network range
        1. 150.5.0.0-150.5.1.255
        2. 150.5.2.0-150.5.3.255
        3. 150.5.4.0-150.5.5.255
        4. ...
4. Scenario 4:
    1. Determine number of networks and convert to Binary
        1. Class A: 10.0.0.0
        2. Need 1000 networks
        3. 1000
        4. 10 bits
    2. Reserve Bits in subnet mask and find your increment
        1. /8 255.0.0.0
        2. 11111111.00000000.00000000.00000000
        3. 11111111.11111111.11000000.00000000
        4. subnet mask 255.255.192.0
        5. increment 64
    3. Use increment to find your network range
        1. 10.0.0.0-10.0.63.255
        2. 10.0.64.0-10.0.123.255
        3. 10.0.128.0-10.191.255
        4. 10.0.192.0-10.0.255.255
        5. 10.1.0.0-...

### Subnetting Based on Hosts

1. Scenario 1:
    1. Determine number of hosts and convert to Binary
        1. 216.21.5.0
        2. 255.255.255.0
        3. 30 user = 5 bits
    2. Reserve Bits in subnet mask and find your increment
        1. 255.255.255.
        2. 11111111.11111111.11111111.00000000
        3. 11111111.11111111.11111111.11100000
        4. CIDR: /27
        5. 255.255.255.224
        6. increment 32
    3. Use increment to find your network range
        1. 216.21.5.0
        2. .32
        3. .64
2. Scenario 2:
    1. Determine number of hosts and convert to Binary
        1. Class C 195.20.0
        2. 50 Hosts = 6 bits
    1. Reserve Bits in subnet mask and find your increment
        1. 11111111.11111111.11111111.00000000
        2. 11111111.11111111.11111111.11000000
        3. CIDR /26
        4. Subnet 255.255.255.192
        5. increment 64
    1. Use increment to find your network range
        1. 195.5.20.0
        2. 195.5.20.64
        3. 195.5.20.128
        4. 195.5.20.192
3. Scenario 3:
    1. Determine number of hosts and convert to Binary
        1. Class B 150.5.0.0
        2. 500 Hosts = 9 bits
    2. Reserve Bits in subnet mask and find your increment
        1. 11111111.11111111.00000000.00000000
        2. 11111111.11111111.11111110.00000000
        3. 255.255.254.0
        4. /23
        5. increment 2
    3. Use increment to find your network range
        1. 150.5.0.0
        2. 150.5.2.0
        3. ...
4. Scenario 4:
    1. Determine number of hosts and convert to Binary
        1. Class A 10.0.0.0/8
        2. 100 hosts = 7 bits
    2. Reserve Bits in subnet mask and find your increment
        1. 11111111.00000000.00000000.00000000
        2. 11111111.11111111.11111111.10000000
        3. 255.255.255.128
        4. CIDR /25
    3. Use increment to find your network range
        1. 10.0.0.0
        2. 10.0.0.128
        3. 10.0.1.0
        4. 10.0.1.128
        5. 10.0.2.0
        6. ....

### The Great Exception

* Because Binary begins Counting from zero...
  * these network values may throw off calculations *
    * 2, 4, 8, 16, 64, 128
  * these host values may throw off calculations
    * 3, 7, 15, 31, 63, 127
* To be Safe
  * Subtract / When Finding Networks *
  * Add /  When Finding Hosts

### Reverse Engineering a Subnet Problem

* Scenario 1:
  * IP: 192.168.1.127
  * Mask: 255.255.255.224
  * The subnet is broken
* Scenario 2:
  * IP 172.16.68.65
  * Mask: 255.255.255.240
  * GW: 172.16.68.62
    * Device has the wrong GW for its IP address

### Variable Length Subnet Mask (VLSM)

* VLSM Scenario
  * Subnet 192.168.1.0/24 to Address this network. Use the most efficient addressing possible.
    * Router 1
      * 20 Users
    * Router 2
      * 20 Users
    * Router 3
      * 60 Users
    * Links between Router
      * 2 users per each link
        * 3 links in total
    * All Routers connected to each other.
  * Start with largest number of users
    * 60 Users
      * 192.168.1.0 - 192.168.1.63/26
      * 255.255.255.192
    * 20 User Networks
      * 192.168.1.64 - 95/27
      * 192.168.1.96 - 127/27
    * 2 users
      * 192.168.1.128 - 131/30
      * 192.168.1.132 - 135/30
      * 192.168.1.136 - 139/30

## Access Lists

### How the Router Became a Firewall

* What is an Access List (ACL)
  * Most Successful hacking attempts come from the inside.
    * What they are: A list of Permit and Deny Statements
      * Permit 192.168.2.50
      * Deny 192.168.1.0/24
      * Permit TCP Port 80 for 200.1.1.1
      * Permit all TCP traffic for 210.0.1.0/24
* Alternative ACL Uses
  * What they can be used for
    * Access Control
    * NAT (Network Address Translation)
    * Quality of Service
    * Demand Dial Routing
    * Policy Routing
    * Route Filtering
    * Making French Toast
* The Rules Governing ACLS
  * Lists are read from Top to Bottom; stops at first match
    * Invisible implicit deny at the bottom
  * ACL is applied to an interface inbound or outbound
* Types of Access Lists
  * Standard Access Lists
    * Matches based on Source address
    * lower processor utilization
    * affect depends on application
  * Extended
    * Matches based on Source/Destination Address, Protocol, Source/Destination Port Number
    * Higher Processor utilization
    * Syntax takes some time to learn
  * Reflexive (Established)
    * Allows return traffic for internal Requests

`ip access-list standard __NAME__`
Allows for named access lists instead of numbers

### Configuring Standard Access Control Lists

* Standard ACL Scenario #1

```text
R1
  conf t
    ip access-list standard SCENARIO1
      deny 10.1.1.1 0.0.0.0 / deny host 10.1.1.1
      permit 0.0.0.0 255.255.255.255 / permit any
    int s0/0 ip access-group SCENARIO1 in
```

* Standard ACL Scenario #2

```text
R1
  conf t
    ip access-list standard SCENARIO2
      deny 192.168.2.0 0.0.0.127
      permit any
    int g0/0
      ip access-group SCENARIO2 out
```

* Standard ACL Scenario #3

```text
R3
  conf t
    access-list 50 deny 192.168.2.50 0.0.0.0
    access-lsit 50 permit any
```

* Bonus

```text
conf t
  ip access-list standard FILTER_TELNET
    permit 10.0.0.0 0.255.255.255
  line vty 0 4
    access-class FILTER_TELNET in
```

* If used for security, apply it as close to the destination as possible.

* You can change the sequence number in the list. This tells it how to execute.

## Network Address translation

### Technology Overview

* What is NAT?
  * Internet = Big Network
  * Too many devices compared to the number of total IP addresses
  * IP management necessary
  * Public and Private Divide Needed
  * Welcome to NAT!
* How NAT Works
  * Originally it was a one to one mechanism
    * This form of NAT is Commonly called PAT (Port Address Translation)
    * PAT
        |Inside Address | Outside Address
        :---:|:---|
        192.168.1.50:6711 | 200.1.1.1:6711
        192.168.1.51:1536 | 200.1.1.1:1536
    * Allows you to over load a single public address, so it can service multiple private interfaces
    * Can see that using `netstat`
    * number of ports available `65,536`
    * `Socket` when the ip address and port are placed together
    * Will translate the port (PAT)
  * Static NAT
    * Static NAT can translate full IP Addresses or Specific Ports
      * Inside Address | Outside Address
        :---:|:---:
        192.168.1.50:6711 | 200.1.1.1:6711
        192.168.1.51 | 200.1.1.2
      * Static NAT are usually for incoming connection
      * Can take 1 ip address and carve it up to send it to multiple internal devices
  * Dynamic NAT

### Configuring NAT Overload

1. Assign IP addresses and connect devices as shown. The computers can be configured via DHCP or statically.
    * Internet 200.1.1.1/24 from G0/1
    * Router to switch 192.168.1.0/24 from G0/0
2. Configure a default
    1. Create ACL to ID Addresses to b e translated
    2. Identify the inside and outside interfaces
    3. Define NAT Operations
    4. ```text
       How to configure NAT Overload
        reload in ?
        ip access-list standard NAT_ADDRESSES
          permit 192.168.1.0 0.0.0.255
          exit
        int g0/0
          ip nat inside
          exit
        int g0/1
          ip nat outside

        ip nat inside source list NAT_ADDRESSES interface g0/1 overload

        sh ip nat translation

        ip nat pool SNUGGLES 200.1.1.2 200.1.1.5 prefix-length 24

        ip nat inside source list NAT_ADDRESSESS pool SNUGGLES overload
       ```

### Configuring Static NAT

```text
ip nat inside source static 192.168.1.50 200.1.1.10

ip nat inside source static tcp 192.168.1.51 80 200.1.1.11 80
ip nat inside source static tcp 192.168.1.51 443 200.1.1.11.443