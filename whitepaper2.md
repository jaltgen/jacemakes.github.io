---
title: Modern Connectivity Whitepaper
date: 15. February 2019
layout: page
---

# High-Availability Secure Networking for Media Companies

## The Need for Speed (and Security)

The revolution is over. Digital acquisition and production of media is here. [Moore's law](https://en.wikipedia.org/wiki/Moore%27s_law) has held true for the past 45+ years. A radical explosion in the speed of electronic information processing has set in motion the most fundamental shifts in the way we process information since the introduction of mechanical movable type printing to western culture by Johannes Gutenberg in ca. 1450. In the field of media production, this digital revolution has brought digital film cameras and audio recording devices that can match almost all analog recording formats in terms of quality, and certainly in the availability of storage quantity. With the digital acquisition of video and audio sources comes the digital distribution of source, intermediate and master material via computer networks.

This reality forces production and postproduction providers to invest in high-performance network infrastructure in their [LAN](https://en.wikipedia.org/wiki/Local_area_network): 10Gbps or even 40Gbps Ethernet over dedicated fibre-optical connections to high-capacity storage solutions are becoming necessary with the increase of both spatial- as well as color-resolution beyond FullHD and 8bit. 4K and larger sources in 10bit, 12bit and beyond are necessary to deliver the quality necessary for high-grade finishing. Such systems generally called "Storage Area Networks" - SANs in short - rely on managed networks provided by business-grade hardware. Consumer routers as provided by Internet Service Providers or switches bought cheap at your local electronics retailer have no place in these networks. Neither do Cat. 5 cables suffice to deliver the throughput you need to keep the work going in your suites.

A crucial requirement that mustn't be overlooked is that of security. With the advantages of server-based post workflows comes the risk of a breach of network security. With all of your production's expensive assets on a series of networked servers, these assets could potentially become accessible from without your LAN. If an intruder gains access to your network through the internet, they may steal, leak or delete your assets, potentially causing significant damage to your business. You may have to restore data from a backup - if there is one, may be liable to pay damages and loose current or future work. It is therefore imperative to plan for adequate network security, even in small post houses or one-man shows when NAS / SAN technology is used.

One aspect so far overlooked is your connection to wide-area networks. While local high-speed connectivity is one pillar of a functioning postproduction, the speed with which you can access wide-area networks (WAN) - e.g. the internet - can severely limit your ability to download assets, upload deliverables to your clients or run backups or archive requests to a cloud. This can foreseeably even be the determining factor in how you must time and offer services, if they require large up- or downloads. Also, in the world of IP based live video production, adequate bandwidth is quintessential to deliver your product.

In this whitepaper I will outline requirements and solutions for:

- increasing bandwidth locally
- network security
- remote internet access

## Maximizing Local Bandwidth

### Network Topology Essentials

Computer networks can be modeled as a number of network nodes connected by links. A node could be a computer, router or a switch, or a number of different devices outside the scope of this paper. Links between those nodes are typically wired copper or fibre-optic connections or wireless signals as Wi-Fi or LTE / 4G. Based on this model, a variety of topologies are conceivable. While now deprecated networking systems such as the Token-Ring system used ring or bus topologies, Ethernet networks are usually constructed of a number of star-type networks with interconnections between individual star-networks being created by connecting the central node of the individual stars.

These central nodes are usually specialized devices to facilitate the distribution of discrete information packages to all or a single receiver specified in the package. Depending on the specific mode of operation, these are called hubs, switches or routers. A hub is a "dumb" device that relays a received package to all other nodes instead of just the desired recipient, thus potentially clogging up the network with much unnecessary traffic. A switch is similar to a hub but it forwards a package only to the recipient as identified by the MAC address specified in the packet. Lastly, routers may look like switches in many ways but operate at the junction between networks. As (CISCO)[https://www.cisco.com/c/en/us/solutions/small-business/resource-center/networking/network-switch-what.html]puts it "Switches create a network. Routers connect networks." A router may also connect networks built with different technologies, such as a Ethernet-based home- or office network and a LTE/4G-wireless network. Routers are also the devices connecting local networks to  the internet usind DSL, T1, leased-lines or other technologies. Routers do this by routing packages based on their IP addresses. This will be explored in more detail later.

Networks can be classified by their size and scope. Most commonly, a local home or office network is called a Local-Area Network (LAN). In a simple case, this is the network created by your router. This router assigns IP addresses in your LAN and routes the requested information to the Wide-Area Network (WAN). It may be technically inaccurate to say that the WAN is the internet, per se, but when connecting to a WAN as provided by Internet Service Providers (ISPs), your intent is to connect to the internet. Beyond the simple case of an ISP-supplied router doing its thing, there are more advanced and advantageous setups to consider to meet your needs.

### Good Physical Connection

To facilitate high-speed connectivity in your local network, a variety of options are available ranging from simple "change the cable" to a more involved process of buying dedicated equipment. The first thing ensure is quality cabling. While conventional copper-wiring is often already available in office spaces, just because it has an [RJ-45](https://en.wikipedia.org/wiki/Modular_connector#8P8C) connector doesn't mean it can deliver the speed you want. Adequate cables, terminators and wall sockets are crucial.

The household-standard network standard, Ethernet, exists since the 1980s and for copper-wired networks, speeds have increased one-thousand-fold in this timeframe, growing from in bandwidth from 10 Megabits per second to 10 Gigabits per second (10Mb/s to 10Gb/s). To put this in perspective for media companies, today, you can theoretically push about 4.5 TeraBytes through a 10Gb-Ethernet connection per hour. For most non-backbone connections, meaning workstations in postproduction suites or on set, that is usually sufficient. Due to the long history of Ethernet, however, if you plug new 10GbE hardware into an old wall socket that is wired with copper cables conforming to the Cat.5E or lower standard, you will not get the speed you desire. Even Cat.6 and above cables that theoretically support 10GbE might fall short if they are bent to sharply, twisted or the shielding has ben cut. This might result in less than ideal data rates on those connections.

In general, it pays to have an expert install cabling to match the speed you wish to achieve. Cat.6 and Cat.6A (augmented) are adequate for patch-cable distances (connecting devices within a 19-inch rack, or bridging the distance from a wall socket to your computer), while the more sturdy Cat.7 cables are more suited for installation in walls or over larger distances. That is only for copper wires, though.

The go-to way to connect devices to facilitate the next jump in connection speed by an order of magnitude is fibre-optic connections. These lightweight, flexible cables carry pulses of light instead of electric current and are already common in many network applications in the form of the [Small Form-Factor Pluggable](https://en.wikipedia.org/wiki/Small_form-factor_pluggable_transceiver#SFP+) - SFP for short. In the enhanced version - SFP+ - they carry up to 10Gbps in an Ethernet network, but the deployment of new form-factors for 40GbE and 100GbE is already under way. In all fairness, even copper wired cables can carry 40GbE in certain configurations.

That is all good and well, though the real question is, how much bandwidth does a postproduction facility require to operate without being disturbed by lagging connections? TB/h is a great metric  if you want to calculate offload times in a data-wrangling situation, yet doesn't say much in terms of how much video editing you can do at once.

### Storage Bandwidth Requirements in Digital Post-Production

The bandwidth with which computers connect to storage is best thought of in terms of video streams. As such the bandwidth requirement of a stream can in simple terms be considered as the bitrate of the codec. Say you have an [Apple ProRes 4444 [PDF]](https://www.apple.com/final-cut-pro/docs/Apple_ProRes_White_Paper.pdf) file in 1920x1080p25, then your data rate is approximately 300 Mbit/s. Clearly, even a 1 GbE connection can provide up to three such streams (as needed in a multicam scenario, for example). This theoretical calculation assumes a great many things, though. It considers a single workstation connected via a 1GbE port is reading a single file from a single storage device connected to a network via a 1GbE connection with no other factors considered.

The reality of a postproduction facility with multiple workstations is quite different. Multiple clients will be reading and writing multiple files to a variety of storage devices. Such a facility will have an online storage solution like an Avid Nexis, TeraBlock or EditShare server, should have a backup "nearline" storage and might have a workstation writing a tape for archival or off-site backup purposes. Suddenly, the demand on the network is significantly higher.

Imagine this network as a series of pipes. All the workstations are connected with pipes of equal bandwidth: capacity per time interval. All these pipes are 10GbE connections that all run into a switch, where a large pipe collects all the water - or data - running into it and distributes it to the network-attached storage via yet another pipe. If we have 10 workstations pushing at full bandwidth, the switch will have to handle 100 Gb/s from the ten 10Gb/s pipes (again: ideal figures ignoring overhead etc.). If all this data is to run into the server, the pipe between switch and server also would have to be 100Gb/s. This is a crucial bottleneck to think about. The NAS must be connected at multiple times the bandwidth of the various clients, or the pipes will not be able to let enough water through, causing a information to be queued for transfer. This becomes lag in applications which an operator will experience and might have to justify to a client.

To adequately design a computer network to handle the demands of digital film post-production, the first question to ask is the required number and bandwidth of simultaneous video streams that will have to be read from the storage solution. A simple offline edit in 1920x1080 without need for multicam editing might get by with just a few streams. When the resolution switches to 4K, all of a sudden, the bandwidth is increased by a factor of four (theoretically). If you run a compositing application like Nuke or AfterEffects, you might be pulling from dozens of video sources at once, some might be 8K or above. Or maybe you are color grading just a few 8K raw files. Either way, these demands have to be figured into the choice of switch and connection to the storage solution. Most definitely, to enable 4K and above or raw workflows, 10GbE is necessary. Further, it is crucial to understand that not all switches are created equal in terms of the internal bandwidth they provide and cheap consumer products often don't provide specifications to evaluate the product. Invariably, professional products should be chosen over ISP-provided hardware.

### The Mare of Direct-Attached Storage

With the reference speeds established above, quick work can be made of evaluating local storage media such as external hard-drives or solid-state drives. It doesn't matter whether using *Just a Bunch of Disks* - JOBDs - or a *Redundant-Array of Independent Disks* - a RAID, locally connecting them means using either the household-standard USB, Thunderbolt or maybe an external SATA port. None of these, by specification,  in a single-cable configuration, pass 10Gb/s of bandwidth. This is assuming that the storage medium itself, the hard-disk or SSD are fast enough to saturate the connection. Depending on USB type (3.1 vs 3.0 vs 2.0) and the Thunderbolt type, these connections can be drastically slower. Also, with USB, the internal bus layout of the computer can dramatically reduce bandwidth. Simply, most Direct-Attached-Storage is slower than modern professional Network-Attached solutions based on the architecture of the connections.

Beyond the technical limitations, DAS solutions are also less secure: hard-drives can be stolen off desks, they can be dropped, a single drive could just fail, incurring significant recovery costs. A server room can be locked and the server backed up. Working on a local drive means a backup solution must be in place at every workstation to ensure quick and effortless failover. Finally, the administration of a multi-suite postproduction workflow with portable storage media is highly inefficient and redundant, since many copies of raw footage have to be created, hard-drives moved and copied over.

On a TV series project for a large German broadcaster in 2018 the estimate for required number of 1TB portable hard-drives was six-thousand. Given 120TB of footage simultaneously available to eight editors with backup and redundancy, an entire office would have been stacked ceiling-high with hard-drives. The server-solution finally deployed was significantly cheaper, faster, more reliable, highly redundant and easier to administer. In short: unless you are working on just one project on one workstation, there is no viable reason to use direct-attached storage. And even then, a networked solution holds advantages.

Tape storage such as [Linear Tape-Open](https://en.wikipedia.org/wiki/Linear_Tape-Open) has been excluded from this analysis, since, while they are amazingly durable and cost-effective, their linear data access mode means they aren't usable as a data source for non-linear editing or visual effects work, as they would have to continuously rewind to play the same clip again.

### Dedicated Pipes: Storage Area Networks

The architectural concept of network-attached storage is that of connecting your storage in the way you would connect any other component to an existing network. Since basic network infrastructure is usually available in offices, connecting a NAS-device is an easy way to supply all connected devices (even mobile devices via wifi) to a shared storage solution. Sharing the same network infrastructure as all other network traffic comes with the disadvantage of important file-access traffic having to share bandwidth with other frames of data such as music streaming, emails, Voice-Over-IP for modern telephone infrastructure. Depending on the configuration of the switches and routers, it might be that some traffic, such as near-real-time VoIP, is prioritized. This could mean delay in the connection to the networked storage.

The solution is to create a secondary network dedicated entirely to the connection of storage infrastructure. This is the concept of Storage Area Networks. Instead of the storage connection sharing a network with all other traffic, the speedy flow of large amounts of data is the sole purpose of this network. Usually, this will be achieved using fibre-optics as the backbone to which clients are connected. Client workstations receive hardware able to connect directly to fibre-optic connections. While this sounds expensive and excessive, one further advantage is that access to such a dedicated network is easier to control. Because no direct connection needs to exist between the SAN and the internet (or Wide-Area Network), such a SAN can potentially be made much more secure than a NAS connected to a LAN with internet access. Of course, NAS systems come with security measures and rights-management systems designed to prevent unsanctioned access, but such means by their nature only prolong the time required to gain unauthorized access. They are not inviolable The route to accessing a SAN is through a client, and unless there is one switched on and connected to the internet, there is no way to access the SAN from the outside.

The idea of buidling and paying for an entirely new network when you really just want to speed your existing connection up may seem counter-intuitive. In reality though, the difference may not be so great. Given you are operating on a Cat.5E, copper-wired Ethernet network, and you wanted to upgrade to 10GbE, new Cat.6 or above cables would have to be installed to facilitate the speed increase. Since the cabling would have to be changed in either case, you could decide to install new fibre-optic cables instead of copper, and lay these in parallel to your existing ones, you could quite easily construct a SAN with a few added pieces of hardware in your server rack. The only connection between the SAN and the internet would be through clients connected to both networks. In the current example, this client's internet connection is maxed at 1Gb/s. Given that WAN speeds rarely exceed 1Gb/s, this should be sufficient in most cases. If you wanted faster up/downlink, you could install a few dedicated 10GbE clients on the slow network.

## Getting Online

### Different Ways to Connect

The market for WAN connections is large and agile with many Internet Service Providers competing for your money. Offers differ mainly in speed, sometimes in volume of data per time interval and often in the way the connection is established. Relevant technologies today are different types of DSL (Digital Subscriber Line), Cable internet, LTE/4G Cellular, satellite, dedicated leased-lines and derived services such as Ethernet-First-Mile (EFM). Most expensive but most adequate for fast, reliable connectivity is the leasing of a dedicated line straight to the service provider. Such systems can today be ordered to match the speed of your local network (yes, 10Gb/s internet is a thing), but at immense cost compared to DSL, T1 or LTE connections. Because the lines are dedicated, connectivity might not be available in certain areas. In any case, cost, speed and availability have to be balanced when choosing an ISP. Beyond the technical choice of your connection, there is more to consider.

### A Safe Front-Door

Connecting your LAN to the services available in the global internet is usually the reason you have a network to begin with. Opening your network to the outside, besides providing essential services to your company, comes with significant risk. You wouldn't leave the main entrance to your premise unlocked at night. Unwittingly, the networks of small and medium sized businesses are often left wide open, though. The first thing you should do to protect your network is this: get a professional router. Almost everything about the routers distributed by ISPs is bad. The wifi antennas are most likely small, the routing options are limited, firewall options are ridiculous, the internal switching bandwidth is small. It might even be throttling certain ports, for example when real-time applications like Voice-Over-IP are active. It is a dangerous, slow piece of junk that has no place in administering a high-performance, secure network. If you can get rid of it entirely by getting a router that can connect to your DSL, T1 or fibre-optics connection, do that. If you cannot get around it, use it strictly as an intermediary between your provider and a new, shiny, professional router.  

Manufacturers like Cisco or Lancom produce routers certified to conform to security standards to reduce the threat of being hacked. Among those features are operating-systems with hardened access rules and no back-doors, built in firewalls closing unused ports, filtering content and many more that cheap routers don't have. This router is the digital front-door of your business - it's locks should be as strong as possible.

The field of network security is wide and entire professions work exclusively to stay ahead of hackers trying to exploit existing hardware flaws, protocol leaks and user errors (such as falling for phishing sites). A few things can easily be done. Relatively low-cost integrated solutions such as (WatchGuard Firebox devices)[https://www.watchguard.com/wgrd-products/network-security-appliances] can be deployed to increase security on-site. If this isn't an option, a DIY-solution could be deploying a single-board computer with content filters in the LAN - though this is by no means a safe catch-all. The take-away should be that network security when connecting to the internet is not a given and action should be taken to prevent potentially ruinous breaches of security.

### What if the door is locked?

Continuing with the door-metaphor, if you simply get a consumer-grade internet access, it is most likely that your ISP doesn't have set guarantees for service availability: your digital front door might be jammed shut up to 5% of the time and you can't get the service provider to fix it. In Germany, for example, ISPs often have a 95% uptime guarantee for a single year in consumer internet services. This means that 365 x 5% = 18,25 days of a year their service might be unavailable and they don't have to do anything about it, legally. In business contracts, these Service Level Agreements might be 99.9% of uptime guarantee. That brings you to about 6 hours of down time in a year. That is already a lot better. In the end, the quality of service you buy must match the degree to which you depend on said service. If, as a postproduction house, you are receiving and delivering content via the internet daily and maybe run backups to a cloud service over night, 18 days of downtime is a definite showstopper.

To get around even statistically small downtimes, you can employ different strategies involving the use of not one but multiple WAN-connections. Essentially, you get multiple internet connections, preferably from multiple ISPs and combine the bandwith. To provide security against a systematic failure of a single service such as ADSL, VDSL, Cable or LTE / 4G, simply combine different WAN connection types from different ISPs. This way, your specialized multi-WAN router can not only failover to a different line should one go down, but in normal operations, it can also use the combined bandwidth of all those connections to provide you with an overall higher bandwidth. Should you be in the situation where no high-speed single line can be had, pairing many slower lines can make up for this disadvantage. As provider of such solutions, Mushroomnetworks.com puts it ("relying on a single point of failure, especially when it comes to the ISP connectivity, is no longer within acceptable SLA and reliability requirements for any serious organization.")[https://www.mushroomnetworks.com/blog/should-you-migrate-your-2-router-2-isp-network-to-a-multi-wan-router-network/]

Multi-WAN systems come in two general categories: load-balancing and bonding. Load-balancing is the simpler technology, which switches different transport protocols (or applications, such as FTP download and upload, VoIP, web traffic, VPN traffic) to different lines. Because the entire traffic of one application can only ever go through one line, the speed of a single application can not be greater than a single line, while there can be more applications running at faster speeds on both lines in parallel. This means load-balancing can be used to increase the number of applications that can run at a given speed, but you cannot increase the speed of, say, a single large file transfer, because all packets always have to go through the same line.

Bonding is a technology where the multi-WAN connected router rips apart discrete packages of data and pushes them through multiple WAN lines. Reassembly of the packet by a remote router is required, however, requiring a second site with another high-grade WAN connection to reassemble and feed the traffic to its final destination. The precise sizing and design of a bonding application is best done by professionals, but the message for businesses suffering from poor connection speeds and quality is, that there are options. Just because your ISP won't dig up your road and front-yard doesn't mean you are forever caught in the hinterlands of bad internet.

### WAN Access On-The-Road

In evaluating WAN connections, it has proved useful to assume the mean speed to be about half of the maximum speed measured. As discussed above, you can lease connections with speeds up to 10Gb/s as of the time of writing in 2019. Consider, though, an old, slow Asynchronous DSL 50.000, providing (on average a mere 36.8 Mb/s of download)[https://www.dslweb.de/dsl-16000-speed-test.php]. Halve this: 18,4 Mb/s of approximate mean speed. In many asynchronous DSL connections, the upload is about 1/5 to 1/4 of the download (since most users download much more than they upload). A fifth of 18,4 Mb/s is 3,68 Mb/s - about the bandwidth needed to stream a medium-quality 720i50 video with stereo audio of appropriate quality.  Therefore, even via an asynchronous, consumer-grade WAN connection, with a security factor of 10, you can broadcast a decent HDReady TV program.

This ubiquitous availability of WAN access has been changing the outside-broadcasting industry. A satellite uplink is no longer the only nor necessarily the best access to sufficient network speeds. LTE / 4G solutions using bonding of multiple SIM-cards are available in portable formats, supporting small news-gathering crews or even larger broadcast productions on locations that were previously unaccessible due to the size and complexity of satellite uplinking equipment. While choosing a simple LTE-bonding backpack as the solution for a run-and-gun news gathering operation, as we have seen, having a single point-of-failure in the form of a single networking technology can threaten productions. Linking multiple types of connections, for example DSL, KA-SAT and LTE into a bonding connection provides double-redundancy plus enhanced bandwidth for streaming, even if one network fails.

The double-redundancy in this system has proved useful in situations where the location of live productions was making the use of a single WAN connection too unreliable. One such production for a small German TV station was troubled by the parking location of the SNG and its satellite dish, so that no KA-SAT connection was available. The event location provided a redundant synchronous DSL line from a premium German ISP. Just two hours before the event, continuous monitoring of the WAN connection showed continually diminishing network speeds. Extrapolation of the trend meant a total failure of the line by the time the broadcast was set to start was likely. Fortunately, the OB-van provided by (IP-Broadcast)[http://ip-broadcast.link/] is fitted with a high-gain LTE-system, so that the production quickly pivoted to LTE as a fallback. This example shows that even a connection that is reputable (premium ISP with business-grade Service Level) and has never failed (according to the location manager) is not a safe bet in a live-situation and provisions should be made for fail-over scenarios. In this case, an (encoder-managed bonding)[http://www.intinor.se/en/products/direkt-link/] with INTINOR Hardware linking a DSL and LTE connection via Lancom WAN-routers was the solution. As the DSL network degraded, the encoder dynamically adjusted both the data rate of the HD broadcast as well as the lines it used, delivering an uninterrupted 5+ hour broadcast without operator intervention.

The ease with which WAN-connections can be accessed today can lure people into a false sense of security, thinking that a single WAN line can be the single uplink to broadcast content. Smart technologies such as multi-WAN bonding have to be deployed to avoid single-point-of-failure scenarios and deliver data as contracted

Another case where on-the-road WAN access can be helpful is in providing communications to cast and crew on location. A professional LTE router with a high-gain directional antenna can provide internet access where smartphones fail to get service. In even more remote situations, a satellite uplink can achieve the same. Providing internet access can not only be important to production management but also to technical crew such as Digital Image Technicians or data wranglers who might want to upload dailies for review.

Whether for broadcast or to establish communications, WAN-access while on location is achievable with redundancy leveraging modern networks and smart fail-over solutions.