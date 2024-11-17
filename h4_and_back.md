## To the moon and back
Source: https://terokarvinen.com/trust-to-blockchain/#homework

### x) Read and summerize
Source: Nakamoto 2008: Bitcoin: A Peer-to-Peer Electronic Cash System (https://bitcoin.org/bitcoin.pdf)  chapters
- 1 Introduction
 - traditional commerce in internert relies heavily on financial institutions
 - third parties always increase costs, because there is possibility to challenge transactions, one must create trust and therefore collect information about parties and certain amount of frauds exists
 - paper proposer digital financial transaction mechanism guaranteed with cryptographical hashes and peer-to-peer network to build it trustworthy
- 2 Transactions
 - digital coin is a chain of signatures
 - owners (previous, recent and future) sign transactions with public keys
 - problem of double-spending is dealt with open and public chain of transactions where you can verify that the money isn't double spent
- 3 Timestamp Server
 - as solution is created chain of hashed time-stamps, which include always the previous hashes.
 - so the last chain consists of all the previous    
- 4 Proof-of-Work
 - one block contains nonce created by proof-of-work
 - proof-of-work is consept of guarantee authenticity of block which contains hash and nonce
 - proof-of-work is price in form of CPU effort that makes it umprofitable to forge blocks
 - as proof-of-work is cpu effort, the longest chain of block is the one that is most valued (effort=value)
 - majority rules - those who have the most CPU power can rule the chain, but because CPU is widely spreaded there is not a one single authority or party to rule it
- 5 Network
 - nodes are important actors in network - nodes have chain of transactions and ability to add new ones and creating nonse
 - longest chain available is the one that is always used
 - if other branches appear - those are cut down whenever new proof-of-work is created
- 6 Incentive
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
- recycle


- ### e)
- e) Explorer. Use a block explorer to analyze a block on the real Bitcoin blockchain.
-  Explain what each value and field means. You only need to analyze the block information and one sample transaction,
-   as a block can contain many transactions. Voluntary bonus: Use a transaction that's interesting,
-   such as one related to a crime or other unusual event.
-   find out Explorer --> https://mempool.space/ (and actually this translates to finnish)
-   ![image](https://github.com/user-attachments/assets/58c6763e-40fd-4193-94c9-74046c493ca8)
-   I pick up real block-->Lohko / block 870556
-   hash 0000000000000000000283a2f61d78a519199af5ca359ef2f51e7915739c9a6c
-   time-stamp 
-   transactio
-   size
-   weight
-   state
-   transaction fee rate
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



