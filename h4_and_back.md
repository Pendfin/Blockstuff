## To the moon and back
Source: https://terokarvinen.com/trust-to-blockchain/#homework

### x) Read and summerize
Source: Nakamoto 2008: Bitcoin: A Peer-to-Peer Electronic Cash System (https://bitcoin.org/bitcoin.pdf)  chapters
#### - 1 Introduction
 - traditional commerce in internert relies heavily on financial institutions
 - third parties always increase costs, because there is possibility to challenge transactions, one must create trust and therefore collect information about parties and certain amount of frauds exists
 - paper proposer digital financial transaction mechanism guaranteed with cryptographical hashes and peer-to-peer network to build it trustworthy
#### - 2 Transactions
 - digital coin is a chain of signatures
 - owners (previous, recent and future) sign transactions with public keys
 - problem of double-spending is dealt with open and public chain of transactions where you can verify that the money isn't double spent
#### - 3 Timestamp Server
 - as solution is created chain of hashed time-stamps, which include always the previous hashes.
 - so the last chain consists of all the previous    
#### - 4 Proof-of-Work
 - one block contains nonce created by proof-of-work
 - proof-of-work is consept of guarantee authenticity of block which contains hash and nonce
 - proof-of-work is price in form of CPU effort that makes it umprofitable to forge blocks
 - as proof-of-work is cpu effort, the longest chain of block is the one that is most valued (effort=value)
 - majority rules - those who have the most CPU power can rule the chain, but because CPU is widely spreaded there is not a one single authority or party to rule it
#### - 5 Network
 - nodes are important actors in network - nodes have chain of transactions and ability to add new ones and creating nonse
 - longest chain available is the one that is always used
 - if other branches appear - those are cut down whenever new proof-of-work is created
#### - 6 Incentive
 - cpu time and electricity are used assets when creating proof-of-work
 - creator of the block receives a new coin
 - transaction fee is a reward when creating the block - it is basically a fee when doing transactions ---> e.g. sending one coin (0.73 value received + 0.27 transaction fee)
 - system is build to support trustworthiness by it being cheaper to be honest than a crook.

### a) Creating the wallet
 - Using againg my virtual machine Debian (ehiich was set up in homework 1 (https://github.com/Pendfin/Blockstuff/blob/main/h1_perttu.md)
 - updating packkages -->sudo apt-get update
 - installing electrum --> sudoapt-get install electrum --> success no error messages 
 - running it --> electrum --testnet
 - Setting it up: automated server connection, new standard wallet, putting seed  and password in safe place, encrypt the wallet also
### b) trying to get some money
-  faucets to be tested
  - today out of order (https://coinfaucet.eu/en/btc-testnet/)
  - seems to be up and running https://bitcoinfaucet.uo1.net/send.php - 
  - Up and running https://tbtc.bitaps.com/tools and also https://faucet.triangleplatform.com/bitcoin/testnet    
- Get an address from my wallet ( and yes it is online)--> error wrong volume --https://bitcoinfaucet.uo1.net/send.php (don't understand what this means?)
- next faucet: https://faucet.triangleplatform.com/bitcoin/testn- Error: Expected property "1" of type Satoshi, got Number -146625 (and after multiple tries the niumber changes)
- my address is correct - if I change it has different kinf of error message
- Test the other site (https://tbtc.bitaps.com/tools)-------diffent kind of messages - not defined
- Check some videos how to solve the problem - total frustration - zero info -should be simple as .....
- taken different approach and actually installing windows app and create new wallet for laptop. Wallet-app called sparrow -->https://sparrowwallet.com/download/ (mainly because i found videos for idiots how to useit [https://www.google.com/search?q=idiots+guide+to+set+up+testnet+bitcon+wallet&oq=idiots+guide+to+set+up+testnet+bitcon+wallet&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIJCAEQIRgKGKAB0gEJMjE5MDJqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8#fpstate=ive&vld=cid:d6be2b75,vid:7JJkLW4SHKQ,st:56](https://youtu.be/7JJkLW4SHKQ))
- After setting it up (just testnet3 version of it) try to receive again
- Same errors ---- checking server status and after testing connections--> manage to acquire some testcoins
- but for a other faucet - same errors
- testing again with my debian and electrum ---- suprpise it worked, i changed the server before trying it again.
- seems like the only faucet working is https://bitcoinfaucet.uo1.net/send.php
- now i have two wallets in two different environments
- note: later those didn't work, but day after https://coinfaucet.eu/en/btc-testnet/ worked again for sprrow 
### c) Giveway. Move money to another Bitcoin wallet. Choose an amount where the last two digists are 73.
- trying to send it fro my sparrow wallet to electrum wallet
- ![image](https://github.com/user-attachments/assets/af32ccc0-fd69-43f8-aa08-4377d43259cb)
- Pending transaction 'Pay 730 sats to tb1qe9xm3yjx85et64x9ugs6tyewcmhemp7tg9vr32' - pay high fee for transaction
- still waiting while going to have dinner
- next day checking the wallets
- ![image](https://github.com/user-attachments/assets/69d96a27-bd34-44ff-937a-361f784ab7ba)
- I can see unconfirmed transactions - have try to change servers because electurm keeps falling offline from time to time

### d)
- recycle- sending it back
![image](https://github.com/user-attachments/assets/acb05b84-9173-4d1b-a92e-baf1f694a11d)
![image](https://github.com/user-attachments/assets/4210f60c-2845-4582-89d9-5685e8b12820)
- not easy to send when someones so little amounts and high transaction fees



### e) Explorer. Use a block explorer to analyze a block on the real Bitcoin blockchain.
-  Explain what each value and field means. You only need to analyze the block information and one sample transaction,
-   as a block can contain many transactions. Voluntary bonus: Use a transaction that's interesting,
-   such as one related to a crime or other unusual event.
-   find out Explorer --> https://mempool.space/ (open source project)
-   ![image](https://github.com/user-attachments/assets/4732c2b2-f289-426c-bbb6-874eed86bde3)

-   I pick up real block--> / block 870556 (https://mempool.space/block/0000000000000000000283a2f61d78a519199af5ca359ef2f51e7915739c9a6c)
-   hash 0000000000000000000283a2f61d78a519199af5ca359ef2f51e7915739c9a6c
-   hash: fingerprint of the block
-   time-stamp:time when block was created
-   size: size of the block, the amount of data in the block
-   weight: weight units - calculated sum of the size of the transactions in block. Differnet parts
-   health: percentage, how many transactions where intentionally exxcluded from block. percentage of expected vs. actual block 
-   transactions: amount of transactiosn in the block
-   total fees
-   miner: whi mined the block

-   state:
-
-    transaction fee rate
-   medium transaction fee
-   sum of transaction fees
-   cost
-   miner
-   one transaction (random) 4066334cdd3e818a011d257e1f79d04b9e66a345e0c00f0770aeda859ab8eadf
-   timestamp
-   properties
-   check
-   transaction fee
-   transaction fee rate
-   miner
-   
### f) rogecoin
source: https://www.youtube.com/watch?v=GUs5y9leCyA
- argument 1 - Digital money is easy to lose (20% forget their passwords).You can lose it also easily by scams or harddisc failure 
  - probably yes, if you don't or cannot use software. Tracebility and coercive measures are not yet on the same level than with fiat money
  - probably no, not more easier than fiat money what is scammed in fastening speed by phones and emails. And whatabout when your house burns and you forget to take the pillow with you....
- argument 2 - It is not widely accepted
  - probably yes, you can't use it everywhere
- argument 3 - It collective hallucination
  - probably yes and no , might be but so it is fiat money. The structures of fiat are older and practises established, but all the same: the value is what we think it is
- argument 4 - It is Hype and full of complicated with technogiberish
  - probably yes - definetely so but isn't all new things (AI?). It's more of feature of product. 
- argument 5 - It is volatile and highly speculative
  - probably yes - because it is not linked in any real asset it's value changes much.
  - probably no - not more than stocks - if you think about what happened with memestocks the story isn't that different
- argument 6 - Fiat currency is printed and backed by lizard people
  - probably yes - definetely - V 
- argument 7 - blockchain is based on needlesly complicated mathproblems
  - probably yes - there might be other solutions for proof-of-work, but none of I know
  - probably no - the proof-of-work is in the core to create trust and value in real peer-to-peer networks  
- argument 8 - uses vast amounts of energy and accelerates climate change
  - probably yes - not as much as some people argue, but rogecoin is not a necessity - we can all live without it. Like among lots of other things too......
- argument 9 - value of rogecoin is based on assumption of goverments falling apart
  - probably yes - in some circles maybe
  - probably no - the value is purely speculative and it has nothing to do with chaos  
- argument 10 - it is investment
  - probably yes - of course, is good or a bad is another story. But like fiat, you don't get anything with you form here  
- argument 11 - GPU's prices are rocketing
  - probably yes - demand of CPU power has been increasing
  - probably no - probably big datacenter supporting AI are increasing prices even more  


