---
title: Modern Connectivity Whitepaper
date: 11. February 2019
layout: page
---

# High-Availability Secure Networking for Media Companies

## The Need for Speed (and Security)

The revolution is over. Digital acquisition and production of media is here. [Moore's law](https://en.wikipedia.org/wiki/Moore%27s_law) has held true for the past 45+ years. A radical explosion in the speed of electronic information processing has set in motion the most fundamental shifts in the way we process information since the introduction of mechanical movable type printing to western culture by Johannes Gutenberg in ca. 1450. In the field of media production, this digital revolution has brought digital film cameras and audio recording devices that can match almost all analog recording formats in terms of quality, and certainly in the availability of storage quantity. With the digital acquisition of video and audio sources comes the digital distribution of source, intermediate and master material via computer networks. 

This reality forces production and postproduction providers to invest in high-performance network infrastructure in their [LAN](https://en.wikipedia.org/wiki/Local_area_network): 10Gbps or even 40Gbps Ethernet over dedicated fibre-optical connections to high-capacity storage solutions are becoming necessary with the increase of both spatial- as well as color-resolution beyond FullHD and 8bit. 4K and larger sources in 10bit, 12bit and beyond are necessary to deliver the quality necessary for high-grade finishing. Such systems generally called "Storage Area Networks" - SANs in short - rely on managed networks provided by business-grade hardware. Consumer routers as provided by Internet Service Providers or switches bought cheap at your local electronics retailer have no place in these networks. Neither do Cat. 5 cables suffice to deliver the throughput you need to keep the work going in your suites.

A crucial requirement that mustn't be overlooked is that of security. With the advantages of server-based post workflows comes the risk of a breach of network security. With all of your production's expensive assets on a series of networked servers, these assets could potentially become accessible from without your LAN. If an intruder gains access to your network through the internet, they may steal, leak or delete your assets, potentially causing significant damage to your business. You may have to restore data from a backup - if there is one, may be liable to pay damages and loose current or future work. It is therefore imperative to plan for adequate network security, even in small post houses or one-man shows when NAS / SAN technology is used.

One aspect so far overlooked is your connection to wide-area networks. While local high-speed connectivity is one pillar of a functioning postproduction, the speed with which you can access wide-area networks (WAN) - e.g. the internet - can severely limit your ability to download assets, upload deliverables to your clients or run backups or archive requests to a cloud. This can foreseeably even be the determining factor in how you must time and offer services, if they require large up- or downloads. Also, in the world of IP based live video production, adequate bandwidth is quintessential to deliver your product.

In this whitepaper I will outline requirements and solutions for these three aspects: 
1) high-speed local connectivity for 4K and above content
2) maintaining accessability and ease of use while ensuring security of assets
3) options to maximize internet bandwidth

## Maximizing Local Bandwidth

### Storage Bandwidth Requirements in Digital Post-Production & Data Wrangling

The bandwidth with which computers connect to storage is best thought of in terms of video streams. The bandwidth requirement of a stream can in simple terms be understood as the bitrate of the codec. Say you have an [Apple ProRes [PDF]](https://www.apple.com/final-cut-pro/docs/Apple_ProRes_White_Paper.pdf) file in 1920x1080p25, then your data rate is approximately 300 Mbit/s. Clearly, even a 1 GbE connection can provide up to three such streams (in a multicam scenario, for example). This theoretical calculation assumes a great many things, though. It considers a single workstation connected via a 1GbE port is reading a single file from a single storage device connected to a network via a 1GbE connection with no other factors considered. 

The reality of a postproduction facility with multiple workstations is quite different. Multiple clients will be reading and writing multiple files to a variety of storage devices. Such a facility will have an online storage solution like an Avid Nexis or TeraBlock server, a backup "nearline" storage and maybe a workstation writing a tape for archival or off-site backup purposes. 


### Good Physical Connection

To facilitate highspeed connectivity in your local network, a variety of options are available ranging from simple "change the cable" to a more involved process of buying dedicated equipment. The first thing ensure is quality cabling. While conventional copper-wiring is often already available, just because it has an [RJ-45](https://en.wikipedia.org/wiki/Modular_connector#8P8C) connector doesn't mean it can deliver the speed you want. Adequate cables, terminators and wall sockets are crucial.

Without going into unnecessary detail, Ethernet exists since the 1980s and for copper-wired networks, speeds have increased one-thousand-fold in this timeframe, growing from in bandwidth from 10 Megabits per second to 10 Gigabits per second (10MbE to 10GbE). To put this in perspective for media companies, today, you can theoretically push about 4.5 TeraBytes through a 10GbE connection per hour. For most non-backbone connections, meaning workstations in postproduction suites or on set, that is usually sufficient. Due to the long history of Ethernet, however, if you plug new 10GbE hardware into an old wall socket that is wired with copper cables conforming to the Cat.5E or lower standard, you will not get the speed you desire. Even Cat.6 and above cables that theoretically support 10GbE might fall short if they are bent to sharply, twisted or the shielding has ben cut. This might result in less than ideal data rates on those connections. 

In general, it pays to have an expert install cabling to match the speed you wish to achieve. Cat.6 and Cat.6A (augmented) are adequate for patch-cable distances (briding devices within a 19-inch rack, or the distance from a wall socket to your computer), while the more sturdy Cat.7 cables are ideal for installation in walls or over larger distances. That is only for copper wires, though.

The go-to way to connect devices to facilitate the next jump in connection speed by an order of magnitude is fibre-optic connections. These lightweight, flexible cables carry pulses of light instead of electric current and are already common in many network applications in the form of the [Small Form-Factor Pluggable](https://en.wikipedia.org/wiki/Small_form-factor_pluggable_transceiver#SFP+) - SFP for short. In the enhanced version - SFP+ - they carry up to 10Gbps in an Ethernet network, but the deployment of new form-factors for 40GbE and 100GbE is already under way. In all fairness, even copper wired cables can carry 40GbE in certain configurations. 

- upgrade to a 10 GE system for your NAS
- throttel certain routes
- make sure to have well-laid, quality cables at each step
- think about bottlenecks. Switches are not created equal.
- install a dedicated SAN, maybe even fibre

With 

# WAN Access

The first thing you should do when upgrading your network is this: get a professional router. Almost everything about the routers distributed by Internet Service Providers is bad. The wifi antennas are most likely small, the routing options are limited, firewall options are ridiculous, the internal switching bandwith is small. It might even be throtteling certain ports, for example when you use Voice-Over-IP. It is a dangerous, slow piece of junk that has no place in adminstering a high-performance, secure network. If you can get rid of it entirely by getting a router that can connect to your DSL, T1 or Fibre Optics connection, do that. If you cannot get around it, use it strictly as an intermediary between your provider and your new, shiny, professional router. From now on, this new router will take care of DHCP, Wifi, VPN, firewalls, throtteling, subnets and so forth. 

- bonding must be accessible for all protocols!
