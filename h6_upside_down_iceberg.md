## Tasks and guidence in https://terokarvinen.com/trust-to-blockchain/#homework

## x) Read and summarize
###  Tor: The second-generation onion router By Dingledine, Mathewson and Syverson 2004:. In USENIX security symposium 

Refenence:Dingledine, R., Mathewson, N., & Syverson, P. F. (2004, August). Tor: The second-generation onion router. In USENIX security symposium (Vol. 4, pp. 303-320). Available at: https://svn-archive.torproject.org/svn/projects/design-paper/tor-design.pdf

Chapter:3 Design goals and assumptions

- Goal is to create anonymous low latency network desing that prevents attackers find out communicating parties
- There are also several evolution directions:
  - it must be easy, cheap and secure to deploy for volunteers providing the service
  - it must be easy to use and implementable to have enough users to blend in
  - it must be flexible for future demands (whatever those might be)
  - it must have simple design to make goals mentioned before achievable
  - due to these goal some goals are excluded - it doesn't provide peer-to-peer,end-to-end or protocol-level protection for users. These might be solved with solutions desgned elsewhere than in orginal design
- Threat model:
  - focusing in adversary who have capabilities to compromise,alter or observe network partially
  - designed to prevent traffic analysis attacks where network weaknesses are analysed based traffic patterns
  - adversary could mainly threaten the reliability and trust against network and lure users to more vulnearable environments to easiers to prey


### De-anonymisation attacks on tor: A survey. By Karunanayake, Ahmed, Malaney, Islam and Jha 2021 In IEEE Communications Surveys & Tutorials 
Reference: Karunanayake, I. et al. (2021) “De-Anonymisation Attacks on Tor: A Survey,” IEEE Communications Surveys and Tutorials, 23(4), pp. 2324–2350. Available at: https://doi.org/10.1109/COMST.2021.3093615.
Chapters:
- Abstract
- I Introduction
- II Background (to the end of "B. Circuit Establishent for Tor HS")
- Fig. 6. Taxonomy for Tor attacks (Just the figure on page 2330.)
#### Summary
- Tor is propably the most used anonymity network
- Anonymity is misused widely into illegal activities but it is also used to avoid injustice from autocracit rules
- that leads to increased urge to control anonymity networks which leads attacks agains anonymity
  - these can come form the authorities side or criminal side 
- The need for anonymity in legal situations has lead projects to create anonymous networks
  - first ones suffered in low-latency
  - article focuses on The Onion router project aka TOR
- The most common attack against TOR is de-anonymise attacks
- As a backlash against these attacks researchers have fixed holes in design and developped ways to keep the anonymity
- Article is about these de-anonymisaion attacks and it presents taxonomy of attacks used and practicalities of those attacks
- Basic consept of TOR is introduced
  - how it is build on circuits with onion proxys (OP), nodes (entry, middle, exit) and hidden services (HS)
    - also components of network like rendezvous points (RP), bridges, service directories (DS), introduction points work and why those are essential for creating anonymity 
  - article describes how circuits are established and what kind of encryption mechanisms are used when securing the connection
    - basically connection is established using installed client which connects with DS and gets lists of free relays and chooses three of them to be entry, middle and exit. Connections are sealed with symmetric keys negotiated via Diffie Hellman Key exchange protocol
  - it also describes how it differs when dealing with 'public' services and when dealing wtih hidden services
  - normal circuits don't hide the service that user is using - in hidden services which support anonymity with so called rendezvous points which hide both communicators identity
- Figure 6 is about categorization of attacks towards TOR
  - it focuses solely on de-anonymization attacks
  - de-anonymization has four subcategories which are labeled based on networks components used in attack
  - active means active participation in traffic, passive is listening
  - last branches are actual attacks/techniques performed
- The idea of figure is to give an overview of different attack types and especialy de-anonymistaion attacks

### PhishSticks - The Ethical Hackers tool for BadUSB (Video) by Halonen, Ollikainen, Rajala 2023
Reference: Halonen, Ollikainen, Rajala 2023: PhishSticks - The Ethical Hackers tool for Bad USB. link: https://www.youtube.com/watch?v=bDzVevtZiWE
#### Summary
 - video is informative video about security measures especially about USB device used to penetration test
 - first yuo lure the user, in this case The Ceo to insert USB-device on his computer
 - it activates windos powershell and starts recording key strokes
 - it stores the data and sends it penetrator via HTTP-mail and deletes it contents after sending
 as a result password is lost, money is lost, freedom is lost


## a)  Install Tor browser and acces Tor network
Reference: https://www.torproject.org/download/ and 
- Doing this on Virtual Machine (Debian GNU/Linux 12/64-bit, Xfce version 4.18) running in Oracle virtual toolbox. And this running in Windows environment (https://github.com/Pendfin/Blockstuff/blob/main/h1_perttu.md )
- First go to the (with firefox) TOR-project web page and download it -->https://www.torproject.org/--> download browser--> there i want to know how to verify browsers signature (https://support.torproject.org/tbb/how-to-verify-signature/)
- checking that my gnupg is up-to-date (sudo apt-get install gnupg) and it is
- fetching developer keys -
  -~$ gpg --auto-key-locate nodefault,wkd --locate-keys torbrowser@torproject.org
gpg: key 4E2C6E8793298290: public key "Tor Browser Developers (signing key) <torbrowser@torproject.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
pub   rsa4096 2014-12-15 [C] [expires: 2027-07-15]
      EF6E286DDA85EA2A4BA7DE684E2C6E8793298290
uid           [ unknown] Tor Browser Developers (signing key) <torbrowser@torproject.org>
sub   rsa4096 2024-07-15 [S] [expires: 2026-10-26]
- so this is the public key used to verify releases --> now create keyring
  - gpg --output ./tor.keyring --export 0xEF6E286DDA85EA2A4BA7DE684E2C6E8793298290
- now I downloaded both files, the actual browser or OP  (Onion proxy)
 - ~/Downloads$ ls
age-v1.2.0-linux-amd64.tar.gz
tor-browser-linux-x86_64-14.0.3.tar.xz
tor-browser-linux-x86_64-14.0.3.tar.xz.asc
- Comfirming it: $ gpgv --keyring ./tor.keyring ~/Downloads/tor-browser-linux-x86_64-14.0.3.tar.xz.asc ~/Downloads/tor-browser-linux-x86_64-14.0.3.tar.xz
gpgv: Signature made ti 26. marraskuuta 2024 05.12.55 EET
gpgv:                using RSA key CAAE408AEBE2288E96FC5D5E157432CF78A65729
gpgv: Good signature from "Tor Browser Developers (signing key) <torbrowser@torproject.org>" --> good to go and install it, nut before that uncompress it with $ tar xf tor-browser-linux-x86_64-14.0.3.tar.xz
- checkiong it from teh desktop - i've checked this so just launch it 
  ![image](https://github.com/user-attachments/assets/48806bbe-aedd-4645-bcd3-fabde5963065)
- and here we go 
  ![image](https://github.com/user-attachments/assets/3fa74ec4-7b8d-46fd-a909-54c9c359e7af)
- checking preferences of my connection (this ins my first time though), not apllying anuy bridges at this point, because it is not forbidden in Finland and my VPN is still here, not changing other preferences but setting security level a bit higher 
- clicking connect--> and it goes to duckduckgo.onion searching for wikipedia
- what happened behind th courtains, below the deck or under the hood--> browser  or OP connected DS (directory service), get nodes for entry, middle and exit
- https://duckduckgogg42xjoc72x3sjasowoarfbgcmvfimaftt6twagswzczad.onion/?q=wikipedia&ia=web
- --> in this case the page is outside TOR it can be seen that the page is visited but my anonymity is guaranteed through TOR-circuit which can be seen in 
![image](https://github.com/user-attachments/assets/1ec0d490-a506-4ea9-9ef1-1b36352c1f0c)

## b) Browse TOR
#### Searching for oninon search engine with duckduckgo
  -  ![image](https://github.com/user-attachments/assets/a0f6c7ff-beb9-482b-8735-79e31f595758)
  -  picking this one:
    -![image](https://github.com/user-attachments/assets/afdbd73c-3d53-41eb-b2c1-cf44c07c91ee)
 - trying to find something e.g. ahmia-->
   -![image](https://github.com/user-attachments/assets/4a460da5-8aa7-484f-8112-23f5880e86b0)
 -also using this
  - ![image](https://github.com/user-attachments/assets/8f83b7ac-0771-4bd5-ab7f-5b5db288782a)
#### Human rights - Peace organisations
- serch in Ahmia - found this
  -![image](https://github.com/user-attachments/assets/1c7ec03c-b2f0-4913-a741-c37c6f8e6a01)
- and with onion engine
  - ![image](https://github.com/user-attachments/assets/74c0e977-c86f-4303-ab02-06896aa0415c)
  - And when searching on the public internet you can find multiple news form the organisations that have also .onion site
  - ![image](https://github.com/user-attachments/assets/b693677c-4a85-48ba-a997-afe230b6a150)
  - after some trying also through the darknet it was found
    - ![image](https://github.com/user-attachments/assets/d13ac9f9-2b36-45cc-8a0f-952f8515871a)
  - not an easy job to use search engine - it has a different logic (like way back in the beginning of www)
#### marketplace
- just hit the saerch engine with marketplace and fing
  - ![image](https://github.com/user-attachments/assets/50bab6b6-cd17-4113-a845-e0b897771501)
- or
  - ![image](https://github.com/user-attachments/assets/5e9e8d0e-9f55-44a3-bdd0-e2658da0b64a)
#### fraud
- is this meaning doing, klearning or being....? first of all lots of sites offer you instructions for fraud e.g the anonymous marketplace
- ![image](https://github.com/user-attachments/assets/37f54cb9-7ecf-4ee2-b2f2-7d0eb840605a)
- and of course where there are malice there are dogooders or maybe those are also fraud
  -  ![image](https://github.com/user-attachments/assets/04cb0fba-52df-4599-af7c-c5b4b6bde2d2)
#### forum
- blinklist has forum
  -![image](https://github.com/user-attachments/assets/145d0c51-0f98-4881-988d-b89d6ffe60ef)
- but it smells fishy, only one post
- almost all the links end up "onion site not found"
-  ![image](https://github.com/user-attachments/assets/47af263a-a868-4b42-887f-79e242b5e37b)
- there are also private forums like or they are scams
  - ![image](https://github.com/user-attachments/assets/35f038c8-27f0-43bb-ace9-67dbbb3ac6b0)
  - ![image](https://github.com/user-attachments/assets/bdd134d5-794e-46cc-be5f-7426b30d8598)
- many forums are more like marketplaces, but you can use Reddit   
#### well known organisation
- amnesty international as was earlier mentioned but also CIA
  - ![image](https://github.com/user-attachments/assets/317d5696-4983-4af9-bcb4-62ada15f338d)
  
- all together it seems that ahmia search engine fetches better sites that are actually online
 
  ## c)Onion. In your own words, how does anonymity work in TOR?
Reference:
- Dingledine, R., Mathewson, N., & Syverson, P. F. (2004, August). Tor: The second-generation onion router. In USENIX security symposium (Vol. 4, pp. 303-320). Available at: https://svn-archive.torproject.org/svn/projects/design-paper/tor-design.pdf
- Karunanayake, I. et al. (2021) “De-Anonymisation Attacks on Tor: A Survey,” IEEE Communications Surveys and Tutorials, 23(4), pp. 2324–2350. Available at: https://doi.org/10.1109/COMST.2021.3093615
- Li, N. (2010). Research on Diffie-Hellman key exchange protocol. https://doi.org/10.1109/ICCET.2010.5485276
- Basyoni, L., Fetais, N., Erbad, A., Mohamed, A., & Guizani, M. (2020). Traffic Analysis Attacks on Tor: A Survey. https://doi.org/10.1109/ICIoT48696.2020.9089497


- so the anonymity is based on layers that don't have access through other layers, the entry node doesn't provide my identity to middle node and middle not to exit node
- encryption used in these layers-->is made layer by layer, meaning it uses Diffie–Hellman handshake (which is explained in simple way and illiustrated [here]([url](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange))).
  - but basically it means that parties agree about parameters that are used to create public keys from their own private keys sharing results with each other and  combining the received public keys  with their own private keys they share keys that can be used to secure communication between them (as long as secrets are safe)
  - keys also change due the limited lifetime of a circuit and rotation of circuit keys
  - actual relays are fixed size and header and paylouad encrypted with 128-bit counter mode Advanced Encryption Standard (AES-CTR), with symmetric keys meaning that those are one time used and not known outside the nodes
  - when hopping out of the onion the traffic is not anymore encrypted if not additional means are used

## d)What kind of the threat models could TOR fit?  
Reference:
  - Dingledine, R., Mathewson, N., & Syverson, P. F. (2004, August). Tor: The second-generation onion router. In USENIX security symposium (Vol. 4, pp. 303-320). Available at: https://svn-archive.torproject.org/svn/projects/design-paper/tor-design.pdf
  - Reference: Karunanayake, I. et al. (2021) “De-Anonymisation Attacks on Tor: A Survey,” IEEE Communications Surveys and Tutorials, 23(4), pp. 2324–2350. Available at: https://doi.org/10.1109/COMST.2021.3093615
  - https://owasp.org/www-project-threat-model/
  - https://github.com/Attacks-on-Tor/Attacks-on-Tor
  - https://onionservices.torproject.org/apps/web/oniongroove/threat/

- threat models that might apply to TOR or more precisely where it could be helpful with?
  - basic feature of TOR is anonymity and the information is not easily available in the network
  - it is not more secure or less secure than public internet if you compromise yourself
  - if communication is or traffic is needed to keep hidden yous hould use onion or hiddenservices
  - threat models that fit for TOR:
    -  traffic and network surveillance - this is commonly used in de-anonymization attacks and it is done by a passive adversary
    -  active adveraries - those can falsify data that is propagated int network
    -  De-anonymization attacks - trying to match the traffic in certain points of network e.g. inbound and outbound
    -  hijacking parts of the network - like in Sybil attact where entry points were created in masses 
  - threats might be involved in industrial espionage, military intelligence operations, free press - basically threat against neeed to communicate anonymously and deliver information in secure way   
 
## e)Don't stick that stick 
 Reference: 
   - PhishSticks on Github (https://github.com/therealhalonen/PhishSticks/)
   - PhishSticks Youtube channel(https://www.youtube.com/@phishsticks_pentest)
   - https://attack.mitre.org

  - Phisticks attack work simply connecting a malicous USB device in a computer. This device actually can contact without actual contact
    - Phistick pretends to be a keyboard and when connected it sends preprgorammed keystrokes to commandpromt or powershell ad executes wanted malice.
    - As it runs you've a split second to realise what has happened as it strokes the commands in
    - In this case it is keystroke listener (but it could be something else) which is designed to record and send keystrokes
    - The spied keystrokes are send via http-mail to wanted address where you can retrieve the outcome and do your evil
  - If you mean a majority of organisation I would guess that they don't have policies against USB devices. But as this said I would continue that larger organisations have. So the typical target is small or medium size organisation
  - Phistick attacks link to  under categories of initial access, execution, credential access, collection and  category or exfiltration in Mitre Att@ck enterprise matrix
  - it is also categorized as malware and used as first step to exploit targeted systems
  - on defenses side this should firstly be 'limit hardware installation' and secondly 'limit software installation'
  - in kill chain this is delivery phase
  - the risk could be mitigated in several ways:
    - disallowing usb-devices by disabling USB-ports
    - using only trusted usb-devices
    - control software of usb-devices
    - user guidence to use only known USB-devices
    - also multifactor authentication would help, because when using stolen credentials it would harder to get in
    -  network intrusion prevention which could monitor unusual traffic going out

## f) Voluntary: I2P. Install and demonstrate use of I2P.

- installing (again environment is-  Virtual Machine (Debian GNU/Linux 12/64-bit, Xfce version 4.18) running in Oracle virtual toolbox. And this running in Windows environment)
- seraching for I2P--> https://geti2p.net/en/--> installing it for debian-- but first dowloaded the keys to verify
  - ![image](https://github.com/user-attachments/assets/cc5416e5-aa36-4202-9cbf-ddeb3c90e7b3)
- sudo apt-get update
- sudo apt-get install apt-transport-https lsb-release curl--> these weren't installed but now those are
- checking my version: $ lsb_release -a
No LSB modules are available.
Distributor ID:	Debian
Description:	Debian GNU/Linux 12 (bookworm)
Release:	12
Codename:	bookworm
 - creating the keyrings
 - $ echo "deb [signed-by=/usr/share/keyrings/i2p-archive-keyring.gpg] https://deb.i2p.net/ $(lsb_release -sc) main" \
  | sudo tee /etc/apt/sources.list.d/i2p.list
deb [signed-by=/usr/share/keyrings/i2p-archive-keyring.gpg] https://deb.i2p.net/ bookworm main
  - $ curl -o i2p-archive-keyring.gpg https://geti2p.net/_static/i2p-archive-keyring.gpg
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 13248  100 13248    0     0  26480      0 --:--:-- --:--:-- --:--:-- 26496
    - verofying the key fingerprint
    - $ gpg --keyid-format long --import --import-options show-only --with-fingerprint i2p-archive-keyring.gpg
gpg: key 67ECE5605BCF1346: 11 signatures not checked due to missing keys
pub   rsa4096/67ECE5605BCF1346 2013-10-10 [SC] [expires: 2025-09-20]
      Key fingerprint = **7840 E761 0F28 B904 7535  49D7 67EC E560 5BCF 1346**
uid                            I2P Debian Package Repository <killyourtv@i2pmail.org>
sub   rsa4096/D241CEBF3CAB5E06 2014-03-21 [S] [expires: 2025-09-20]
-copying ht e keyrings--> $ sudo cp i2p-archive-keyring.gpg /usr/share/keyrings
- getting the I2P repository
  - $ sudo apt-get update
Get:1 https://deb.i2p.net bookworm InRelease [30,9 kB]                         
Hit:2 http://deb.debian.org/debian bookworm InRelease                          
Get:3 http://security.debian.org/debian-security bookworm-security InRelease [48,0 kB]
Hit:4 http://deb.debian.org/debian bookworm-updates InRelease
Hit:5 http://deb.debian.org/debian bookworm-backports InRelease
Get:6 https://deb.i2p.net bookworm/main amd64 Packages [1 924 B]
Fetched 80,8 kB in 4s (22,9 kB/s)       
Reading package lists... Done
- now installing it sudo apt-get install i2p i2p-keyring--> complete and success
- configuring with instruction from here
- ![image](https://github.com/user-attachments/assets/6526c7b7-5f85-42be-8bd4-e88978a0c521)
- and i can see tunnels
- ![image](https://github.com/user-attachments/assets/e0fb62dc-8751-4363-828f-77b87b4f936e)
- so how to find these pages? check them in the reddit--> learning to use address book
- ![image](https://github.com/user-attachments/assets/6781ce55-34b0-4569-a207-0b7aa5f5a857)
- a lot less stuff than in TOR, but neatly available in address book
- and again feels like back in nineties
- ![image](https://github.com/user-attachments/assets/106d3473-c781-4ddd-a999-1fa2a9f72ee0)

 

 

## g) Voluntary: Hyphanet. Install and demonstrate use of Hyphanet.
## h) Voluntary: Freenet. Install and demonstrate use of Freenet.
## i) Voluntary: GNUnet. Install and demonstrate use of GNUnet
