# h1 Adversarial mindset by Perttu
Homework guidance is found https://terokarvinen.com/trust-to-blockchain/#r2-blockchain-to-cryptocurrency
# X

##  Summaries:
  
  ## Cyber Kill Chain
  Source https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf
  
  - Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains - describes necessity to be proactive while defending your assets in digital reality
  - In history aproach has been reactive and adversaries are thought to be always atleast one step ahead of defenders
  - Kill chain is methodological approach to detect, mitigate and prevent cyberthreats
  - it presents indicators (atomic, computed and behaviroal) which are revealed and used to recognize what are the proceudres and methods of adversaries
  - The Kill chain is defined as following phases: reconnaissance, weaponization, delivery, exploitation, installation, command and control, and actions on objectives
  - Paper defines a matrix with phases and action (detect, deny, disrupt, degrade, deceive, destroy) taken in every phase
  - Paper points out that all phases must be analysed
  - Here aplies also 'shift left' thinking. This means moving focus in the process or in this case in chain to things that are happening first (but of course not forgetting things happening on the right). If you are able to build up capabilities to e.g. detect threats in delivery phase it better and cheaper than in later phases
  
  ## Darknet diaries
  Episodes 99: SPY and 100:NSO
  Sources https://darknetdiaries.com/transcript/99/ and https://darknetdiaries.com/transcript/100/
  
  -  story about spies, citizen lab (an independet oraganisation to help people in digital threats), journalists and Israeli techcompany
  -  Spyware was created back in 2012
  -  journalist and activists got wind about foul play using the spyware
  -  some shady means were tried to surpres the investigation of foul play
  -  activist and journalist outwitted the spy and exposed him
  -  no-one got caught but some suspicions were against the developer of spyware
  -  using spyware against citizens when trying to prevent terrorist acts - nodays even more important question: where we draw the line? Is there any ethics if sell your weapons to dictators
  -  who is responsible if you sell spyware as a business?
  
  ## Mitre ATT&ck / enterprise matrix 
    source: https://attack.mitre.org/matrices/enterprise/ and https://attack.mitre.org/resources/faq/
  - ### "tactic"
    - main category for enterprise matrix
    - consist of multiple techniques
    - the why - what are trying to achieve with its techniques
    - example - Reconnaissance - to gather information about the object(s)
      --> old times this could be done with binoculars and microphones (and why not these days also). E.g. you acquire blueprints of the premises, find out the software used. Jira, Confluence, Miro etc....
  - ### "technique"
    - in Att&ck context is a "How to execute attack" - detailed description of attack
    - Vertical in matrix under one tactic
    - Can contain sub-techniques
    - the how - how to achieve the goal
    - Example -Gather Victim Org Information --> e.g. Business relationships
        --> you can pretend to be salesman in conference and pry victims hardware vendors    
  - ### "procedure"
    - implementation of technique that is used
    - can containg several techniques
    - chain of events/actions and tools to implement evil
      - LAPSUS$ Recruiting employees to give access to their employers network and thrpugh that gather information about the software and technical environment 
    
# A
Cyber kill chain vs. ATT&CK enterprise matrix

sources: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf and https://attack.mitre.org/matrices/enterprise/ and https://attack.mitre.org/resources/faq/

- Kill chain is more like a methodology and process to control attacks, it gives you concepts to create capabilities how to analyze and act when incident is or has happened and between incidents
- ATT&CK is knowledge base of tactics and techniques described as matrixes -
- Tactics in ATT&CK and Kill Chain phases are somewhat similar and has (in my understandind) same purpose - to describe what adversary is trying to achieve
- But in when in Kill Chain the phases are sequential and one incident has all the phases ATT&CK describes more detailed tactics for each phase
- ATT&CK also includes techniques which include examples of procedures but also means to mitegate and detect the technique
- Kill chain is more how to do and ATT&CK what to do

# B
Security incident

source https://darknetdiaries.com/transcript/99/ and https://darknetdiaries.com/transcript/100/

Pegasus - not an actual incident, but multiple incidents. And maybe still going strong from year 2012. Pegasus is weaponized malware, a product to make business, build to be sold and exploited by state-level operators, maybe anyone who has enough money and power. The customer data of the company is unknown so you can't be sure. Pegasus was spyware to exploit multiple zero-day vulnerabilities and it first emerged on Ios. It being spyware, its main target is individuals and their mobile device. It could be used for reconnaisance purposes, to know where the person was, who the target was communicating. Basically anything that one did with its phone, state secrets, business secrets, criminal activity etc. Only a actors imagination is the limit. 

The exploit had three stages - 

1 .click the link e.g in text message from your partner. Clicking activates javascript via browser. Javascript exploits a bug in browser's engine. That allows the script upload spyware to phone  
2. Because the target devices were iPhones they needed to use two another exploits to make it possible to be run in the phone   
3. Actual app is then run on the phone and it uses normal phone features. It can turn on the camera,microphone, read messages or listen calls etc.

Basically Pegasus exploited three unknown vulnerabilities in phone and one for user. Adversary send text message for victim. Message was could be very agressively designed. What would you say when you get message that your daughter is in the hospital and the text message telling you this includes link to provide more information about accident. This would of course need some reconnaissance (e.g. social media) beforehand to know your soft spots.

# C
Instal debia on virtualbox 
source guide in https://terokarvinen.com/2021/install-debian-on-virtualbox/

OS:
Version	Windows 10 Pro
Version	22H2
So build 19045.5011

# installing
  1 .Installing image from suggested source: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/  
    ![image](https://github.com/user-attachments/assets/d9d927d5-d09b-46fd-8d19-03604eaaa2ee) --> success  
  
  2. Downloading virtualbox for Windows hosts from https://www.virtualbox.org/wiki/Downloads  
  
  3. Running the Virtualbox installer (v 7.1.4) - accepting permissions - reading license agreement - approving it -   
    ![image](https://github.com/user-attachments/assets/847cc586-9c78-4493-8ec5-959a5f2e737d)
 - agreeing all the other
    steps and starting installation --> success  
  
  5. Starting Virtualbox - choosing expert mode 
  
  6. Starting to create VM    
    ![image](https://github.com/user-attachments/assets/34a8c1b2-de0a-43eb-83d6-b7b781da1294) 
    ![image](https://github.com/user-attachments/assets/85081707-5d0f-49d7-b4aa-7dd051bd6f56)  
and then Finish  
  
  6. Voilá  
    ![image](https://github.com/user-attachments/assets/6e1bfd75-b745-429c-8af7-f4f335a0cd08)
  --> success
     
  8. Putting CD in   
    ![image](https://github.com/user-attachments/assets/cae8d31d-bf95-4e78-ae2c-c265faf2e076)
    ![image](https://github.com/user-attachments/assets/8865ac77-92c1-4018-ab6c-ade3e88c366b)
  --> success
     
  10. Powering up  
    ![image](https://github.com/user-attachments/assets/9215a249-89cd-4bfe-a160-01da00ade3a4)  
  --> success
      
  12. Testing (not so quick though)  
    Firing up Firefox  
    ![image](https://github.com/user-attachments/assets/8b3a0759-5379-49e8-a42d-15e969df96c0)  
Mouse and keyboard working  
    --> success
  11. Installing Debian 
    ![image](https://github.com/user-attachments/assets/d402cea0-5275-49eb-addb-965735de227b)
    --> success
  12. Starting up.......
    ![image](https://github.com/user-attachments/assets/cc0ca68b-acba-4e6f-9688-a000342ba728)
    --> success
  13. Setting up with sudo's 
    ![image](https://github.com/user-attachments/assets/f78deb0d-74bc-4af9-8018-9dfcd4c5da47)
          Upgrading....
    ![image](https://github.com/user-attachments/assets/87b51bbc-4485-43ab-8aba-c11e315ee421)
      --> success

  14. installing firewall   
    ![image](https://github.com/user-attachments/assets/e48bf5ae-aa44-453e-bcb5-f8d91ac8c617)
    --> success

Fixing the screen with the guide - BIG MISTAKE - went bad to worse uninstalled the existing version and lost it. No new one was availble
But then I found the way to rescale it and fix the shared clipboard through the menu (View and Devices). Always check the version you're playing with.
Snapshot taken.
--> success

## D


## E
Fundamentals of infosec.
As updating this voluntary task in last yards of course. I think this has couple of viewpoints:
 - First: Confidentiality, integrity, availability and non-repudiation or CIA (Confidentiality, integrity, availability)-triad. Confidentiality - protect your data from the eyes and tenticles of others, integrity - you can trust your data hasn't been altered, availability - your data, your rules to handle it. 
 - Second: Chaos of the world - the game of adversaries and defenders. Even though principles are good it is important to understand how things happen in real world. To understand potential weaknesses and evilness that might be happening around you. And this with real life examples. How to destroy confidentiality - how i can crack your passwords? How can i disintegrate your data by adding it some small details and availability- what if I deny your access to your data?

References: 
- Andress, J. 2019. Foundations of Information Security. No Starch Press
- EC-Council University - What Are the Fundamentals of Information Security?https://www.eccu.edu/blog/cybersecurity/fundamentals-of-information-security/

## F
