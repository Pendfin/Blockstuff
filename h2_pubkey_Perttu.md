These homeworks and links are from https://terokarvinen.com/trust-to-blockchain/#r2-blockchain-to-cryptocurrency

##  Task x) Read and summarize (with some bullet points)

### Overview of Applied Cryptography by Bruce Schneier 
Chapters explains basic concepts of symmetric cryptography, digital signature and random sequences.
It also describes controversial history of who invented public key and some weaknesses of applications.
Source: Schneier, B. 2015. chapters 2.5-2.8 Applied cryptography, second edition: Protocols, algorithms, and source code in C. 20th anniversary edition ; Second edition. Indianapolis, IN: Wiley.(https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/
#### Chapter 2.5 communications using symmetric cryptography
  - history of public key. Invented in 1976 by Whitfield Diffie and Martin Hellman
  - simple analogy to mailbox. Anyone can send message, but only few or one can read it
  - key management is easier, when you don't hacve to deliver and worry safekeeping of all the secret keys. You just have to agree about the cryptosystem used
  - some ambiguity about the discovery and acceptance of the public kry cryptosystems
  - public key is slower than symmetric algorithms and that is way it should be used to encrypt keys
  - public key is vulnerable against chose-plaintext attacks (key is public and if plaintext ha limited possibilities one can try out to break the message)
  - Merkl's puzzle is a application of public key
#### Chapter 2.6 digital signatures
  - signatures have been a proof of authenticity. In digital world you have to have different approach towards the problem than in manual world
  - arbitrator can be used when using symmetric cryptosystems
  - abitrator is trusted party in messaging and guarantees the autheniticity of messages and messengees
  - arbitror is bottleneck in communication and it needs to absolutely secury and trustworthy
  - works is theory but not in practice
  - signing documents is basically simple with public-private key pairs
  - there are also usecases where you can try to cheat (copy) the document and for that reason you can add data e.g. timestamp to signature
  - problem is when documents become larger and crypting them with public-lkey algorithms are too innefficient
  - you can circumvent this problem with hash functions. With hash functions you can also have multiple signatures in  one document
  - nonrepudiation of signature is hard to ensure, but you can use arbitrator to minimize the risk
#### 2.7. digital signatures with encryption
  - you should use one algorithm or key when encrypting and other when decrypting
  - one feature is to resend the message back as a receipt to sender, 
  - there are multiple ways to attack against public keys, one is to substitute keys in Key distribution scenter
#### 2.8 random and pseudo-random sequence generation
  - in computer it is impossible to create real random sequences and many of existing ones are poor
  - random generators are important in cryptography
  - but you can build good enough pseudo-random generators
  - pseudo-random sequence looks random. The sequence should be as long as you need random number
  - Cryptographic demands for swecure pseudo-random sequence are: it looks random,unpredictability, not reproducerable

 
 Source: Rosenbaum, K 2019. Grokking Bitcoin. Manning Publications (https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/)

### Chapter 2. Cryptographic hash functions and digital signatures by Kalle Rosenbaum
  Chapter 2 of Rosenbaum's book Grokking Bitcoin (Rosenbaum, K 2019. Grokking Bitcoin. Manning Publications (https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/) presents a simplified examples of consepts of blockchain, hash, hash function, digital signature, public and secret key.  In the it presents dilemma of security vs. usabilility (in large sense of usability). Most secure ways of keeping e.g. your private key safe are the most inconvinient ways.
Source: Rosenbaum, K 2019. Grokking Bitcoin. Manning Publications (https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/)

#### Some bullet point
  - Cookien token - you can create your own cryptocurrency - simplified approach to Bitcoin
  - cryptorgraphic hash = digital fingerprint, one of the main
  - hash - and hash function  - hash is fingerprint or a unique stamp which is created with hash function. Hash function is mathematic algorithm to convert your data to hash. Which is though almost always unique.
    -  four basic propertiesof hash fuunction:
      -  The same input will always produce the same hash.
      -  Slightly different inputs will produce very different hashes.
      -  The hash is always of the same fixed size. For SHA256, it’s 256 bits.
      -  Brute-force trial and error is the only known way to find an input that gives a certain hash
    - the last on has three properties
      - collision resistance - you try to create same hash with different sources (almost impossible)
      - pre-image resistance - you try to create the known hash with different sources
      - second pre-image resistance  - you try to create the known hash with different source when you know the original source
  - hash function is one way function so you can't reverse engineer it. Meaning even though you now the outcome and function you can't create all the possible sourcese
  - Digital signature uses private-public key pairs
  - Private key to sign and public key to verify signature
  - Derivation function is one-way function to create public key from your private key
  - You can use private-public key pairs also for communication when using public key to encrypt the message. Bitcon uses only private key for encrypting so anyone can decrypt crypted contains e.g. when digitally signing
   
    



Source: Karvinen 2023: PGP - Send Encrypted and Signed Message - gpg

### a) Pubkey today.

Explain how you have used public key cryptography today or yesterday, outside of this homework. In addition to naming the system, identify how different parties use keys in different steps of the system. (Answering this question likely requries finding sources on your own. This subtask does not require tests with a computer.)

When doing my thesis I have to
Whatsapp - when senging message
HTTPS : Pankkiasiointi

Source https://www.ibm.com/think/topics/public-key-infrastructure
https://en.wikipedia.org/wiki/End-to-end_encryption

### b) Messaging.

Send an encrypted and signed message using PGP, then verify and decrypt it. (You can use folders to simulate users, or use two computers or two different OS users. Don't use Tero as a name of any party, unless that's your given name.)

### c) Other tool. 
Encrypt a message using a tool other than PGP. Explain how different parties use different keys at different stages of operation. Evaluate the security of the tool you've chosen.

### d) Eve and Mallory.

In many crypto stories, Eve is a passive eavesdropper, listening on the wire. Mallory malliciously modifies the messages. Explain how PGP protects against Mallory and Eve. Be specific what features, which use of keys and which flags in the command are related to this protection. (This subtasks does not require tests with a computer)

### f) Password management. 

Demonstrate use of a password manager. What kind of attacks take advantage of people not using password managers? (You can use any password manager, some examples include pass and KeePassXC.)

### g) Refer to sources. 

Verify each homework report (this and the earlier ones) refers to sources. Every homework report should refer to this task page. It should also have references to any other source used, such as web pages, LLMs, man pages, other reports... References are mandatory, and must be present in every report. (This subtask does not need a report, you can just do it and write "Done." as the answer for this subtask.)
