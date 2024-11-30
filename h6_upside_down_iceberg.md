## Tasks and guidence in https://terokarvinen.com/trust-to-blockchain/#homework

## x)
###  Tor: The second-generation onion router By Dingledine, Mathewson and Syverson 2004:. In USENIX security symposium 

Refenence:Dingledine, R., Mathewson, N., & Syverson, P. F. (2004, August). Tor: The second-generation onion router. In USENIX security symposium (Vol. 4, pp. 303-320).

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
