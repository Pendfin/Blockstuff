## Helsec 21.11. public meetings presentations overviews
Source of this recap is livestream of the event 21.11.2024 @[helsec](https://helsec.fi/events/2024-11-21_helsec_november_2024_meetup/)
This recap is created with help of  Microsoft Copilot. It is used to help with abreviations and terminology.

### Industrial Cyber Security by Jos Helmich
Jos talked mainly about his contribution in ENISA. ENISA or European union agency for cybersecurity is a European Union agency to maintain and develop regulation, processes, services, certification schemes concerning cybersecurity and be there for Member states and EU bodies. It also is preparing for future challenges and helping other to do it so too.
ENISA has a vital role when creating directives and acts which are the way that joint legislation and interoperatibility is created in Union.
Jos's role in Enisa is to be part of the Advisory group, which main task is to prepare cybersecurity regulations and produce documentation eg. whitepapers about them. Examples of these are: GDPR(General Data Protection Regulation), NIS2(Network and Information Systems Directive, build on NIS), CRA (Cyber Resilience Act) and AIA (Artificial Intelligence Act). The difference between directive and act is that directive is objective that Member States needs to implement the way that suites them best and act is a law that enforces regulation. So directives implementation can vary from country to country and act is the same everywhere. This differs a lot from how the closest tradepartner USA applies regulations. In USA it based on memorandums, which are more like guidance and clarifications or policies and executive orders, which might be temporary directives from the President of The Unitade States. It is important to understand this difference due to the relationship between Europe and America. Even though one might think we're on the same side in a world where everyone tries to have vantage regulation is one of the key assets to control your own playground.

NIS2 is directive which has a large impact on organisations and it enhances supervision, risk management and reporting requirements. Basicaly It is about organisations cybersecurity. NIS2 is seen in manufacturing industry to approach cybersecurity from risk managements poin of view. Priorities differ from office cybersecurity where confidentiality, integrity and availability are the most important capbilities in this order. And when those capabilities being the same in manufacturing cybersecurity the order is different. First one is availability, then integrity and last confidentiality. This paradigm differentation helps you to design e.g. secure environments which are regulation compliant and functional for office and industrial networks.(https://www.enisa.europa.eu/topics/cybersecurity-education/awareness-campaigns/network-and-information-systems-directive-2-nis2)

CRA being act it is more like a rulebook with rules not to do bad things. It is aimed for cybersecurity of products with digital elements. As it tells more precisely what not to do or do it is recommende to create standards and certifications to adress it. For example the ISO62443 is a good standard tio start with industrial cybersecurity. (Facts checked with help of copilot). So when waiting CRA to be effective it is good to prepare with existing standards. (https://www.enisa.europa.eu/publications/public-consultation-on-specifications-for-euicc-certification-under-the-eucc-scheme)

AIA is also in proposal state and it has a modular and riskbased approach to ensure safe and secure utilization of artificial intelligence. Modular approach means that act consist of separate modules that create a agile entity. The risk approach means that it categorises risks to unacceptable, high risks and AI with specific transparency obligations and minimal risks. Risk framework is build on EU values of fundamental freedoms. (https://artificialintelligenceact.eu/the-act/)

Some questions were addressed to Jos. Some regarded responsible party to overwatch these acts, incident reports and its management and who pays Jos's work effort for Enisa :)


### State of Union by Heikki ”zokol” Juva
Source: https://github.com/Zokol/RED-CRA/blob/main/RED%20evaluation.png - this is presenters github-page

Heikki's presentation was about Eurepean Union regulation, mainly RED (Radio Equipoment Directive) and CRA (Cyber Resilience Act). In previous recap is explained differences of directice and act. And also what is CRA. Presentation included also practical aproach towards how regulation is addressed or taken account in manufacturing of equipments that are objects of regulation.
RED is Radio Equipoment Directive. It is about requirements for radio equipment like baby monitors, earphones etc. In this digital era almost all the devices can be plugged into network. Being so, those should be compliant to RED. In the future CRA is replacing RED as being more coercive. But at the moment RED is enforced and CRA is in 'to-be' state. It is assumed that CRA will be enforced 2027 and lessons learned from RED will be part of it.


RED has also device classification in three layers. First on being connected devices, personal data (like video) using device  and financial data using devices. These layers have different kind of requirements which should addressed in documentation. Especially in terms & conditions part of it.

RED has 'good' and 'problematic' requirements. Good ones are requirements to coordinate vulnerabilities between manufacturers and report vulnerabilities, it also enforces input validation, addresses used cryptrography, password practises and for some parts content filtering. The problematic ones are compatibility which allows less secure solutions when compability is required to older versions, security solutions ourtsourcing to vendors or subcontractors meaning that solution can have external device that takes care of security and last one is that only documentation is used for evaluation of the product. And the documentation is delivered by manufacturer. 

Heikki presented how they tested most popular consumer electronic devices that should be compliant to RED. As case example was IP camera for child monitoring, which had sensors for movement, twoway voice capabilities, wifi-connectivity and cloud to store the data. So based on this it was classified for lauyer 1 and 2 but not three.
The device was practically torn to pieces and its flash memory hacked. Some of the findings were positive and some dubious. Positive ones were that updates are enforced, passwords were crypted well enough and the documentation was in most parts good. The Negative ones were that it did'nt have any kind of physical  protection against bypassing the interface and connect directly to device, passwords were hard coded, like you network details, you probably couldn't wipe it totally clean and documentation had direct flaws like challenging GDPR (by using this device you accept that this is not GDPR compliant).

Overall statistics about the top-ten consumer devices had though pretty good statistics. Most of the devices were using TLS and CERT-pinning (network security), most of them don't have operating systems (this is two-bladed sword), most of them are wifi-connected but don't be onlinen all the time, which narrows probabilities to be hacked. Most common issues were that data is not removed, 3rd party access to ypour information and complex manufacturing/supply-chains. Last one meaning that product is usually piled up form pieces of electronics, software and plastics which can all be outsourced to someone in somewhere.

Some questions were addressed again

Crossfire between markets, business, trust and security. If only done in paper, but auditors power and costs

RED: https://single-market-economy.ec.europa.eu/sectors/electrical-and-electronic-engineering-industries-eei/radio-equipment-directive-red_en



### My experiences on Defender External Attack Surface Management by Joona "Rinorragi" Immonen


### Overall thoughts about the event and topic:
The event it self seemed to be organized pretty well, though presentations were not available and stream was just video of the stage. Some voice problems from time to time.

The topics were interesting (even though the most interesting one for me was flash-talk about European cybersecurity challenge 2024(https://ecsc2024.it/) and Team Finlands experiences in the competition. Seventh out of 37 is not bad.



