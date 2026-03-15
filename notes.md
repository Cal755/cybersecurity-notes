So a private IP is like 192. and some other numbers, which is kinda like the home/host one. The public one is ones people could see from, lets say, an IP grabber and so on.
DNS is just a phonebook for the internet. You know the name but not the number, so DNS looks it up. Instead of typing 104.26.10.229 you just type tryhackme.com and it figures out the IP for you.
Domain endings are called TLDs. Two types gTLD (generic) like .com .org .edu and ccTLD (country code) like .ca .co.uk. So in tryhackme.com, .com is the TLD and tryhackme is the Second Level Domain. Max 63 characters, only a-z, 0-9 and hyphens allowed. A subdomain sits to the left of the Second Level Domain like admin.tryhackme.com where admin is the subdomain. Same rules apply, max 63 characters each and the whole thing cant go over 253 characters total.
DNS Record Types - A Record points to an IPv4. AAAA Record points to an IPv6. CNAME is basically a nickname, like store.tryhackme.com just pointing to shops.shopify.com instead of an IP. MX is where emails go, has a priority number so if the main server is down it tries a backup. TXT is just a text note, used for proving you own the domain or blocking spam.
DNS Lookup - computer checks its own memory first (cache). Nothing there, asks your Recursive DNS Server which is usually your ISP. They ask the Root Server (the big boss). Root points to the TLD Server. TLD points to the Authoritative Server which has the actual answer, also called the nameserver for that domain. Think of it like asking someone who asks someone who asks the person who actually knows.
TTL = how long the answer gets saved before it expires and has to be looked up again. Its measured in seconds.
HTTP is what's used whenever you view a website. HTTPS is just the secure version - data is encrypted so nobody can see what you're sending or receiving and it makes sure you're talking to the right server not a fake one.
A URL (Uniform Resource Locator) is just instructions on how to access something on the internet. It has different parts - Scheme is the protocol like http, https or ftp. User is a username and password if the site needs login. Host is the domain or IP of the server. Port is which port to connect on, 80 for HTTP and 443 for HTTPS. Path is which specific page you want. Query String is extra info sent to the page like ?id=1. Fragment jumps you to a specific section on the page like #task3.
HTTP Methods - GET is for getting info from a web server, POST is for submitting data, PUT is for updating existing data, DELETE is for removing data. Main ones to remember are GET and POST.
HTTP Status Codes - 100-199 info response (barely seen), 200-299 success, 300-399 redirection, 400-499 client errors, 500-599 server errors. Common ones - 200 OK, 201 Created, 301 Permanent redirect, 302 Temporary redirect, 400 Bad Request, 401 Not Authorised, 403 Forbidden, 404 Page Not Found, 405 Method Not Allowed, 500 Internal Server Error, 503 Service Unavailable.
Headers are just extra bits of data sent along with requests and responses. Ones your browser sends - Host tells the server which website you want, User-Agent tells it what browser you're using, Content-Length tells it how much data to expect, Cookie sends your saved cookie data back. Ones the server sends back - Content-Type tells you what kind of data is coming back like HTML or images, Set-Cookie saves a cookie to your computer, Cache-Control is how long to store the response before fetching it again.
Cookies are just small bits of data stored on your computer. When a server sends a Set-Cookie header your browser saves it and sends it back every time you visit. This is how websites remember who you are since HTTP is stateless and doesn't remember previous requests on its own. Usually used for keeping you logged in - stores a token not your actual password.
Websites have two sides. Front end (client side) is what your browser renders and what you actually see. Back end (server side) is the server processing your request and sending the response back.
Websites are built with three things - HTML which is the structure and what the page is built with, CSS which is the styling that makes it look good, and JavaScript which adds interactivity and functionality. HTML is written in elements also known as tags like h1 for headings and p for paragraphs.
Sensitive data exposure is when a developer accidentally leaves login credentials, hidden links or private info in the page source code. As a defender one of the first things you check on a web app is the page source - you can view it by right clicking any website and hitting View Page Source.
HTML Injection is when a website doesnt sanitize user input properly and a user can inject their own HTML code into the page and manipulate it. If JavaScript is injected instead thats called XSS (Cross Site Scripting). The general rule is never trust user input - always sanitize it.
Your computer asks DNS for the IP, connects via HTTP, server sends back HTML, CSS and JavaScript which your browser displays.
Load Balancer = splits traffic across multiple servers so one doesnt get overwhelmed. Does health checks to make sure servers are up. Algorithms are round robin (takes turns) or weighted (sends to least busy).
CDN (Content Delivery Network) = hosts static files worldwide and delivers from the closest server to you.
Database = stores and recalls data for the website.
WAF (Web Application Firewall) = sits between you and the server, blocks attacks, bots and rate limits suspicious IPs.
Web Server = listens for incoming connections and serves web content via HTTP. Common ones are Apache, Nginx and IIS.
Virtual Hosts = lets one server host multiple websites with different domain names.
Static content = never changes like images and CSS. Dynamic content = changes based on requests like a blog.
Backend = behind the scenes code you cant see, languages like PHP and Python. Frontend = everything you see in the browser.
Virtualisation = running multiple VMs on one physical server to save cost and resources.
Hypervisor = software that manages and splits hardware between VMs. Type 1 runs directly on hardware like data centers. Type 2 runs inside an existing OS like VirtualBox, used for home labs and testing. As a cybersecurity person you'll use Type 2 for your home lab.
VM (Virtual Machine) = a full isolated virtual computer inside a physical one. Used in cybersecurity to safely test malware or run tools like Kali Linux without risking your main machine.
Container = lighter than a VM, shares the host OS, runs a single app. Docker is the tool used to run containers.
Cloud Computing = using computing resources over the internet instead of your own hardware. Saves cost, scales easily and accessible globally.
Public Cloud = shared cloud anyone can use, most common, used by most websites and apps like Netflix. Private Cloud = dedicated to one company, used by banks and government for sensitive data. Hybrid Cloud = mix of both, used when you need some things private but still want to scale publicly.
IaaS (Infrastructure as a Service) = you rent the servers and manage everything yourself. Most control. PaaS (Platform as a Service) = provider manages the infrastructure, you just build and deploy your app. SaaS (Software as a Service) = you just use the software over the internet, provider manages everything. Like Gmail or Zoom.
Key cloud benefits - scalability, high availability, pay per use and global access.
Main cloud providers - AWS is the biggest overall. Azure (Microsoft) is most common in enterprise and SOC environments. GCP (Google Cloud) is third.
OS (Operating System) = the core software that manages everything between you, your apps and the hardware.
Kernel Space = privileged core of the OS, has direct hardware access, only the OS runs here. Keeping this separate from user space is important for security - a compromised app cant take over the whole system.
User Space = where normal apps run with limited permissions, cant touch hardware directly.
GUI = graphical interface, clicking icons and windows. What most people use.
CLI = text based commands, way more powerful, used constantly in cybersecurity.
OS Types: Desktop = Windows, macOS, Linux for personal use. Server = Linux or Windows Server, runs websites and databases, usually no GUI. Mobile = Android and iOS. Embedded = lightweight OS in devices like routers and smart TVs. Virtual/Cloud = lightweight OS running in VMs or containers.
As a SOC analyst you'll mainly deal with Windows (enterprise environments run it) and Linux (most security tools run on it).
Windows account types - Guest (minimal permissions), Standard (everyday use), Administrator (full control). Important for understanding privilege escalation.
Task Manager = monitors running processes, CPU/memory usage and logged in users. Used by SOC analysts to spot suspicious processes.
Windows Security = built in security dashboard. Four sections - Virus and threat protection, Firewall and network protection, App and browser control, Device security.
Windows Defender Firewall = built in firewall monitoring network traffic. Three profiles - Domain (organisation networks), Private (home/lab), Public (untrusted like public WiFi).
Windows Update = keeps the OS patched and secure. Unpatched systems are one of the biggest attack vectors so always keep it updated.
CIA Triad = the 3 core principles of cybersecurity. When an incident happens you always ask which of these was affected.
Confidentiality = only the right people can see it. Broken by things like stealing login credentials or intercepting data on public WiFi.
Integrity = data hasnt been tampered with. Broken by things like modifying a bank transfer or changing a grade without permission.
Availability = accessible when you need it. Broken by things like a DDoS attack taking down a website.
Security mindset questions: Was sensitive data exposed to unauthorized individuals? = Confidentiality Was data modified without permission? = Integrity Were systems unavailable when needed? = Availability
Plaintext = readable data. Ciphertext = scrambled unreadable data.
Key = the secret that controls the scrambling. Algorithm = the public method for using the key. Security comes from keeping the key secret not the algorithm.
Symmetric Encryption = one key encrypts and decrypts. Fast but the problem is how do you safely share that one key. If someone intercepts the key they can decrypt everything.
Asymmetric Encryption = two keys, public key anyone can use, private key only you have. Encrypts with public key, only private key can decrypt it. Solves the key sharing problem because you never have to share your private key.
HTTPS hybrid approach = asymmetric encryption shares the key safely first, then symmetric takes over for speed. Best of both.
Certificate Authority (CA) = trusted organisation that signs certificates proving a public key actually belongs to who it says it does. That's what the padlock in your browser means.
SOC (Security Operations Center) = a dedicated team that monitors an organisations network 24/7 to detect and respond to threats.
SOC pillars - People, Process, Technology.
People - the SOC team: SOC Analyst Level 1 = first responder, does basic alert triage and reports detections. SOC Analyst Level 2 = deeper investigation, correlates data from multiple sources. SOC Analyst Level 3 = experienced, proactively hunts threats and handles incident response. Security Engineer = deploys and configures security solutions. Detection Engineer = creates the rules that detect harmful activity. SOC Manager = manages the team and reports to the CISO.
Process - the 5 Ws of alert triage: What = what happened. When = when did it happen. Where = where did it happen. Who = who was involved. Why = why did it happen.
Technology - key tools: SIEM = collects logs from everything and detects suspicious activity through rules. Detection only. EDR = monitors endpoints in real time and can respond automatically. Firewall = monitors incoming and outgoing network traffic and blocks unauthorized stuff.
Security structure - CEO at top, CISO manages security departments, SOC analysts report up through that chain.
Red Team = offensive security, pentesters and ethical hackers finding vulnerabilities. Blue Team = defensive security, SOC analysts and engineers protecting and monitoring. GRC Team = manages policies and compliance with regulations.
CIRT (Cyber Incident Response Team) = the firefighters. Called in when an incident goes critical or out of control. Also called CSIRT or CERT.
Internal SOC vs MSSP: Internal SOC = you work for one company, calmer pace, fewer tools to learn. MSSP (Managed Security Service Provider) = outsourced SOC company protecting multiple clients, high pressure, great for learning fast.
SOC career path = L1 → L2 → Engineer or CIRT or management → eventually CISO.
Humans = weakest link in cybersecurity. Easier to trick a person than hack a firewall.
Social Engineering = manipulating human psychology to gain access. Uses trust and emotion like urgency or fear.
Attack types: Phishing = fake emails stealing credentials. Malware Downloads = tricking victims into installing malicious software. Deepfakes = AI impersonating trusted people. Impersonation = pretending to be IT or colleagues to gain access.
Mitigation = preventing attacks. Detection = catching what slips through. SOC analysts do both.
Key mitigations: Anti-phishing = blocks phishing emails automatically. Antivirus/EDR = stops malware on devices. Security awareness training = teaches employees to spot attacks. Access management policy = documents how IT verifies requests like password resets.
Systems = where data actually lives. Compromising one system can give access to thousands of accounts.
Lateral movement = after getting into one system an attacker moves through the network to find more valuable targets.
Ways attackers get into systems: Weak credentials = stolen or weak passwords, 81% of breaches involve this. Vulnerabilities = flaws in software that get exploited. Each one gets a CVE number. Supply chain attacks = malware hidden in trusted software updates or libraries. Misconfigurations = human mistakes during setup like weak passwords or exposed databases.
Zero-day = a vulnerability with no available fix yet. Most dangerous type.
CVE = unique ID given to every known vulnerability so defenders can track and patch them.
How to respond: Vulnerability found = patch it immediately. Misconfiguration found = fix the setup, patching wont help. Zero-day = restrict access, apply workarounds until a patch is available.
System mitigations: Patch management = keep everything updated. Security awareness training for IT = reduces misconfiguration mistakes. Network protection = restrict access to trusted users only. Antivirus/EDR = stops known malware automatically.
Switches are basically what connects devices together physically, like the actual box with cables plugged into it. You could have one switch for 10 devices and another for the other 10 if you had 20 in total, with both connecting up to the router. Its different from subnetting tho, subnetting is more so the rules of how the network is divided up like HR getting 192.168.1.x and Finance getting 192.168.2.x, while the switch is the physical thing that makes it happen. A layer 2 switch runs on MAC addresses only and cant operate at layer 3. A layer 3 switch can perform some responsibilities of a router tho, meaning it can function on both IP addresses and MAC addresses.
Subnetting is splitting a network into smaller sections like having a HR one and Finance one under certain rules with the subnet set up. Its used mainly for security so different departments cant see each others traffic, performance so theres less congestion, and organisation so its easier to manage. Also remember usable devices = 254 (256 minus .0 network address and .255 broadcast). The .0 for a network is kinda like the street for it and .1 to .254 are the house numbers. Private IP = 192.168.x.x, 10.x.x.x or 172.16.x.x.
Broadcast address is like the megaphone in a sense, which lets them figure out where the device is, kinda like a student at a seat or who it is.
The DHCP gives out the IP addresses when a device connects to the network. Then the ARP sorts them all out by getting the MAC which is perm like a fingerprint and unique, with the first half being where it came from and the other half being the unique part. To add onto the MAC address thing, the ARP also requires the IP address which is like a house that can change, but helps the ARP remember regardless.
DHCP Discover is the one who looks for a new IP address (aka the device). Then the DHCP Offer gives out an IP address, e.g. 192.168.1.10. The DHCP Request takes that IP, then the DHCP ACK says you could use that for 24 hours for example. The ACK time can also be from 1 minute to infinite (not literally but its a metaphor). The shortform for it is DORA - Discover which finds a device that needs an IP, Offer which is the DHCP server saying here take 192.168.1.10 as an example, Request which is the device saying yes ill take it, and ACK which confirms its yours for said amount of time.
Encapsulation is basically like a letter that keeps getting more stuff added onto it as it travels down the OSI layers. Starts as just raw data then each layer wraps it with more info like where its going, which device its for and so on. Going down the layers (7 to 1) is encapsulation which is adding the layers, going back up (1 to 7) is decapsulation which is stripping them back off until you get the original data. Like wrapping a parcel on the way out and unwrapping it on the way in.
Packets are small pieces of data sent from a webserver, put into frames and sent to the computer. The source address is the IP address the packet is being sent from so the data knows where to return to. The destination address is the devices IP address the packet is being sent to so the data knows where to travel to. Packets have IP addressing info while frames have MAC addressing info instead.
TCP is reliable because it requires a lot of back and forth confirmations. Checksum is what gives TCP integrity and the flag tells computers how to handle the packet.
The TCP 3 way handshake goes SYN, SYN/ACK, ACK. SYN says can you hear me, SYN/ACK says yes I can hear you, and ACK says okay great. ACK basically means acknowledge. Once the handshake is done they can start passing data.
To close the connection it goes FIN/ACK saying im all done, then the other side responds FIN/ACK saying yeah me too, then a final ACK saying goodbye. Think of it like two people ending a conversation but its computers instead.
UDP is stateless which means theres no acknowledgement that the other side got the data, it just keeps sending regardless of whether it was received or not. This is why its faster than TCP since it doesnt wait around for confirmations. A good example would be a request getting 3 constant responses just firing over and over. TCP would be used for transferring a file, UDP would be used for a video call.
TCP which means Transmission Control Protocol is used in emails, games and anything that requires a good connection and all files to be properly received. TCP checks every packet arrived correctly before moving on, slower but way more reliable. UDP which means User Datagram Protocol is used for stuff like streams or video calls because you need to send a lot of data and packets at once and they all need to be quick, so it doesnt matter if a few things are off like some pixels missing. UDP just fires packets and doesnt check if they all arrived, faster but some can get lost. To add onto TCP, its basically just small bits of data called packets, like splitting a cat image into thirds, top, middle and bottom, and reassembling them at the other end.
Ports are like places on a computer where we can send and receive data, think of a port where ships go to dock. Depending on whats being sent it goes to a different port like ships going to different docking areas. Ports go from 0 to 65535 and 0 to 1024 are known as common ports. A lot of traffic comes through port 80 which is HTTP and could come from different ports too but 80 is the usual. Some common ones to remember:
HTTP = 80 HTTPS = 443 SSH = 22 lets you remotely access and control another device securely FTP = 21 used for transferring files between devices
Port forwarding is basically telling the router which specific device to send incoming traffic to, since all devices on a network share the same public IP. Like telling a visitor which room to go to in a house. An example of this would be making a webserver on network 1 accessible to the public using network 1s public IP. Without it the router just stands there not knowing which device to send the traffic to.
Firewalls come in two types, stateless and stateful. A stateless firewall looks at individual packets only - what port its coming from, where its going and what protocol its using. If it doesnt meet the requirements it gets blocked. A stateful firewall takes into account the entire connection, not just individual packets, and if something doesnt meet its requirements it can block the whole device, not just the packet. So if someone is doing an attack through port 80 you would configure the firewall to block that IP address entirely.
VPN which means Virtual Private Network allows devices to connect to each other like a tunnel connected and secure like a private network even over the internet. PPP only encrypts and provides authentication of data. PPTP allows the data from PPP to travel and leave a network. IPsec is used by VPN technology to secure the data being sent through the tunnel.
Routers connect networks together and pass data, always taking the most optimal path to get there. A router connects networks while a switch connects devices within a network - worth remembering the difference.
VLAN which means Virtual Local Area Network allows devices within a network to be split up and treated as separate networks even though they arent. Like Sales department (VLAN 1) having an IP of 192.168.1.1 and Accounting department (VLAN 2) having an IP of 192.168.2.1. A switch can act like a router by sending stuff to certain departments in this case, and it helps with security and organisation. Its different from subnetting tho - with subnetting youre creating distinct networks that are completely separate from each other with their own router, while with VLAN youre creating tiny little networks that are virtually separated without needing their own router.
Full packet journey example, first the ARP figures out whos who by matching the MAC address to an IP address. Then a TCP handshake happens back and forth. After that the TCP packet containing the actual data can finally be sent. So ARP first, handshake second, data third.
The OSI model has 7 layers and data travels down when sending and back up when receiving. Each layer has its own job.
Memory trick for the layers bottom to top: Please Do Not Throw Sausage Pizza Away (Physical, Data Link, Network, Transport, Session, Presentation, Application)
Layer 7 - Application is the one you actually interact with, stuff like browsers and emails. Layer 6 - Presentation translates the data and handles encryption and compression, kinda like a translator. Layer 5 - Session manages the connection between two devices, opens it, keeps it alive and closes it when done. Layer 4 - Transport is TCP and UDP, where data gets split into packets and either checked (TCP) or just fired off (UDP). Layer 3 - Network is where routing happens and deals with IP addresses, making sure packets take the most optimal path. OSPF finds the fastest/shortest path while RIP counts how many routers the data has to pass through to get there. Layer 2 - Data Link is where the MAC address gets added to the packet. The MAC comes from the NIC which is unique and permanent to that card. Layer 1 - Physical is literally just electrical signals transferring data in binary, 1s and 0s.
Acronyms
• OSI = Open Systems Interconnection
• TCP = Transmission Control Protocol
• UDP = User Datagram Protocol
• DHCP = Dynamic Host Configuration Protocol
• ARP = Address Resolution Protocol
• MAC = Media Access Control
• IP = Internet Protocol
• NIC = Network Interface Card
• OSPF = Open Shortest Path First
• RIP = Routing Information Protocol
• HTTP = Hypertext Transfer Protocol
• HTTPS = Hypertext Transfer Protocol Secure
• SSH = Secure Shell
• FTP = File Transfer Protocol
• VPN = Virtual Private Network
• PPP = Point-to-Point Protocol
• PPTP = Point-to-Point Tunneling Protocol
• IPsec = Internet Protocol Security
• VLAN = Virtual Local Area Network
• DNS = Domain Name System
• TLD = Top-Level Domain
• ccTLD = Country Code Top-Level Domain
• gTLD = Generic Top-Level Domain
• CNAME = Canonical Name
• MX = Mail Exchanger
• TTL = Time To Live
• URL = Uniform Resource Locator
• HTML = Hypertext Markup Language
• CSS = Cascading Style Sheets
• JS = JavaScript
• XSS = Cross-Site Scripting
• CDN = Content Delivery Network
• WAF = Web Application Firewall
• VM = Virtual Machine
• IaaS = Infrastructure as a Service
• PaaS = Platform as a Service
• SaaS = Software as a Service
• AWS = Amazon Web Services
• OS = Operating System
• GUI = Graphical User Interface
• CLI = Command Line Interface
• CIA = Confidentiality, Integrity, Availability
• CA = Certificate Authority
• SOC = Security Operations Center
• SIEM = Security Information and Event Management
• EDR = Endpoint Detection and Response
• CISO = Chief Information Security Officer
• CIRT = Cyber Incident Response Team
• MSSP = Managed Security Service Provider
• GRC = Governance, Risk, and Compliance
• CVE = Common Vulnerabilities and Exposures


