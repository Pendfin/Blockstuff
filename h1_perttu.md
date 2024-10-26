# X Summaries:
  
  ## Cyber Kill Chain
    https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf
  ## Darknet diaries
    Episodes 99: SPY and 100:NSO
    (https://darknetdiaries.com/transcript/99/and https://darknetdiaries.com/transcript/100/)
    - story about spies, citizen lab (an independet oraganisation to help people in digital threats), journalists and Israeli techcompany
    - Spyware was created back in 2012
    - journalist and activists got wind about foul play using the spyware
    - some shady means were tried to surpres the investigation of foul play
    - activist and journalist outwitted the spy and exposed him
    - no-one got caught but some suspicions were against the developer of spyware
    - using spyware against citizens when trying to prevent terrorist acts - nodays even more important question: where we draw the line? Is there any ethics if sell your weapons to dictators.
    - who is responsible if you sell spyware as a business
  ## Mitre ATT&ck / enterprise matrix 
    (source: https://attack.mitre.org/matrices/enterprise/ and https://attack.mitre.org/resources/faq/)
  - ### "tactic"
    - main category for enterprise matrix
    - consist of multiple techniques
    - the why - what are trying to achieve with its techniques
    - example - Reconnaissance - to gather information about the object(s)
      --> old times this could be done with binoculars and microphones (and why not these days also). E.g. you acquire blueprints of the premises, find out the software used for Jira, Confluence, Miro etc....
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
Cyber kill chanin vs. ATT&CK enterprise matrix

# B
Security incident
 Pick a security incident and learn about it. Write briefly about it. Point out the concepts of threat actor, exploit, vulnerability and (business) impact. (You can find writeups about security incidents from Darknet Diaries and Krebs)
 (source https://darknetdiaries.com/transcript/99/and https://darknetdiaries.com/transcript/100/)
 Pegasus - not an actual incident, but multiple incidents. And maybe still going strong from year 2012. Pegasus is weaponized malware, a product to make business, build to be sold and exploited by state-level operators, maybe anyone who has enough money and power. The customer data of the company is unknown so you can't be sure. Pegasus was spyware to exploit multiple zero-day vulnerabilities and it first emerged on Ios. It being spyware, its main target is individuals and their mobile device. It could be used for reconnaisance purposes, to know where the person was, who the target was communicating. Basically anything that one did with its phone, state secrets, business secrets, criminal activity etc. Only a actors imagination is the limit. 
The exploit had three stages - 
   1 .click the link e.g in text message from your partner. Clicking activates javascript via browser. Javascript exploits a bug in browser's engine. That allows the script upload spyware to phone  
   2. Because the target devices were iPhones they needed to use two another exploits to make it possible to be run in the phone
   3.Actual app is then run on the phone and it uses normal phone features. It can turn on the camera,microphone, read messages or listen calls etc.
   Basically it exploited three unknown vulnerabilities in phone and one for user - the message could be very agressively designed or what would you say when you get message that yous daughter is in the hospital and the link is to provide more information about it.

# C
Instal debia on virtualbox (Using guide in https://terokarvinen.com/2021/install-debian-on-virtualbox/)
Report your work, including the environment (including host OS, the real physical computer used), the steps you took and their results.
Version	Windows 10 Pro
Version	22H2
So build 19045.5011

# installing
  1 .Installing image from suggested source: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/
    ![image](https://github.com/user-attachments/assets/d9d927d5-d09b-46fd-8d19-03604eaaa2ee)
  
  2. Downloading virtualbox for Windows hosts from https://www.virtualbox.org/wiki/Downloads
  
  3. Running the Virtualbox installer (v 7.1.4) - accepting permissions - reading license agreement - approving it - 
    ![image](https://github.com/user-attachments/assets/847cc586-9c78-4493-8ec5-959a5f2e737d) - agreeing all the other
    steps and starting installation
  
  4. Starting Virtualbox - choosing expert mode
  
  5. Starting to create VM 
    ![image](https://github.com/user-attachments/assets/34a8c1b2-de0a-43eb-83d6-b7b781da1294) 
    ![image](https://github.com/user-attachments/assets/85081707-5d0f-49d7-b4aa-7dd051bd6f56)
  
    and then Finish
  
  6. Voilá
    ![image](https://github.com/user-attachments/assets/6e1bfd75-b745-429c-8af7-f4f335a0cd08)
  
  7. Putting CD in 
    ![image](https://github.com/user-attachments/assets/cae8d31d-bf95-4e78-ae2c-c265faf2e076)
    ![image](https://github.com/user-attachments/assets/8865ac77-92c1-4018-ab6c-ade3e88c366b)
  
  8. Powering up
    ![image](https://github.com/user-attachments/assets/9215a249-89cd-4bfe-a160-01da00ade3a4)
  
  9. Testing (not so quick though)
    Firing up Firefox
    ![image](https://github.com/user-attachments/assets/8b3a0759-5379-49e8-a42d-15e969df96c0)

    Mouse and keyboard working
  
  11. Installing Debian
    ![image](https://github.com/user-attachments/assets/d402cea0-5275-49eb-addb-965735de227b)
  
  12. Starting up.......
    ![image](https://github.com/user-attachments/assets/cc0ca68b-acba-4e6f-9688-a000342ba728)
  
  13. Setting up with sudo's
    ![image](https://github.com/user-attachments/assets/f78deb0d-74bc-4af9-8018-9dfcd4c5da47)

      Upgrading....
      ![image](https://github.com/user-attachments/assets/87b51bbc-4485-43ab-8aba-c11e315ee421)

  14. installing firewall
    ![image](https://github.com/user-attachments/assets/e48bf5ae-aa44-453e-bcb5-f8d91ac8c617)

Fixing the screen with the guide - BIG MISTAKE - went bad to worse uninstalled the existing version and lost it. No new one was availble
But then I found the way to rescale it and fix the shared clipboard through the menu (View and Devices). Always check the version you're playing with.
Snapshot taken.









## D


## E


## F
