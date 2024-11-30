## Tasks and guidence in https://terokarvinen.com/trust-to-blockchain/#homework

## x)
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


### x)  De-anonymisation attacks on tor: A survey. By Karunanayake, Ahmed, Malaney, Islam and Jha 2021 In IEEE Communications Surveys & Tutorials 
Reference: Karunanayake, I. et al. (2021) “De-Anonymisation Attacks on Tor: A Survey,” IEEE Communications Surveys and Tutorials, 23(4), pp. 2324–2350. Available at: https://doi.org/10.1109/COMST.2021.3093615.
Chapters:
- Abstract
- I Introduction
- II Background (to the end of "B. Circuit Establishent for Tor HS")
- Fig. 6. Taxonomy for Tor attacks (Just the figure on page 2330.)

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
  - article describes how circuits are established and what kind of encryption mechanisms are used
- Figure 6 is about categorization of attacks towards TOR
  - it focuses solely on de-anonymization attacks
  - de-anonymization has four subcategories which are labeled based on networks components used in attack
  - active means active participation in traffic, passive is listening
  - last branches are actual attacks/techniques performed
- The idea of figure is to give an overview of different attack types and especialy de-anonymistaion attacks
