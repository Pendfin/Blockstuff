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

 
### Chapter 2. Cryptographic hash functions and digital signatures by Kalle Rosenbaum
Chapter 2 of Rosenbaum's book Grokking Bitcoin (Rosenbaum, K 2019. Grokking Bitcoin. Manning Publications (https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/) presents a simplified examples of consepts of blockchain, hash, hash function, digital signature, public and secret key.  In the it presents dilemma of security vs. usabilility (in large sense of usability). Most secure ways of keeping e.g. your private key safe are the most inconvinient ways.
Source: Rosenbaum, K 2019. Grokking Bitcoin. Manning Publications (https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/)

#### Some bullet points
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
   
    
### Overview of PGP - Send Encrypted and Signed Message
Guide to send encrypted messages describes how to create public and private keys, how to simulate creating the trust each other and detailed instructions how to sen crypted messages with gpg.

Source: Karvinen 2023: PGP - Send Encrypted and Signed Message - gpg (https://terokarvinen.com/2023/pgp-encrypt-sign-verify/)
  

### a) Pubkey today.

I know I used banking services to pay the bills - and basically it works like this
When logging in https website you actually use transport layer security (TLS)
TLS provides  
 - encryption
 - authentication
 - integrity
All starts with handshake, knowing each other and version, cipher suites, identities and generating the session keys which are used to encrypt future messaging. TLS uses public key cryptography to find the right keys for our sessions, but also authentication. Server proves its authenticity with private-key crypted message wich I at my end can verify with public key.

Sources:
https://en.wikipedia.org/wiki/Public_key_infrastructure
https://www.identity.com/digital-certificates-key-to-secure-online-transactions/#Understanding_Public_Key_Infrastructure_PKI_and_Its_Role_in_Digital_Certificates
https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/
https://www.cloudflare.com/learning/ssl/how-does-public-key-encryption-work/

### b) Messaging.
Send an encrypted and signed message using PGP, then verify and decrypt it. (You can use folders to simulate users, or use two computers or two different OS users. Don't use Tero as a name of any party, unless that's your given name.)

#### Let's go
Using https://terokarvinen.com/2023/pgp-encrypt-sign-verify/ as guide to crawl through this task
Doing this on with Virtual Machine (Debian GNU/Linux 12/64-bit, Xfce version 4.18) running in Oracle virtual toolbox.
If interest exact steps -  you can find more detailed logs here https://github.com/Pendfin/Blockstuff/blob/main/h2_logs.md
1. Installing the tools (gpg) - done, even though newest version claimed to be in VM still installed micro
2. Generating the key with the name Perttu Salo DEMO KEY  for email perttus@example.com.invalid, no passphase
3. Generating complete, we have a keypair for Perttu, and exported to perttus.pub file
4. Now creating Alice to communicate with. Alice is a folder in my home directory
5. Create the configuration files to make it possibly to create separate keys
6. Created own keypair for Alice to be able to simulate communication
7. Distribute Perttus public key to Alice (copy from home folder to Alice's), and now I can see both keys in Alice's keyring
8. Signing the key to make it trusted  - and in perttus we trust
9. Do it another way around - delivering alice's public key to Perttus and trusting it
10. And now writing message with editor -
11. "Hi Perttus
This is my try-out to establish a secret connection with you.
Hope it goes well.
Alice"
12. Encrypted the message with perttus public key and sing it using alice's private key
13. Send the pigeon! So iI just copy the created crypted file from Alice's folder to Perttus
14. Perttus decrypts the message with his private key and can confirm (with Alice public key) that it was signed with alice private key
15. So perttus send the respond back. Encrypts teh message with Alices public key and signs teh message with his private key
16. Alice decryots the message with her private key and verify the signature with Perttus public key
17. Well-done


### c) Other tool. 
Encrypt a message using a tool other than PGP. Explain how different parties use different keys at different stages of operation. Evaluate the security of the tool you've chosen.
Proton
openssh - you can establish remote secure remote connection with it and it encrypts all the traffic



### d) Eve and Mallory.
Using sources: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/ and https://github.com/Pendfin/Blockstuff/blob/main/h2_logs.md

In many crypto stories, Eve is a passive eavesdropper, listening on the wire. Mallory malliciously modifies the messages. Explain how PGP protects against Mallory and Eve. Be specific what features, which use of keys and which flags in the command are related to this protection. (This subtasks does not require tests with a computer)
 PGP protects in multiple ways messaging:
   - creating the keypairs --- gpg --gen -key for yourself, into your own directory, normally with passphrase.
   - --> this is prerequisite for using keypairs - if you don't have it you can't use gpg
   - exporting keys --- gpg --export--> you can export your public key to file and publish where ever you like. This makes it possible to receive encrypted messages or verify signatures
   - signing the to be trusted ---- gpg --sign -key.- You sign a spesific key you have chosen to trust. It is now saved to keyring.
   - --> this trust makes using of public keys possible and crypting them against eavesdorpping
   - encrypting the message --- gpg --encrypt --recipient, this determines what public key should be used for encryption
   - --> this makes it extremely hard to eavesdrop the message while in transit 
   - signing of the message --- gpg --sign (without any flags it uses senders private key)
   - --> this verifies the message to be authentic (if my private key hasn't been stolen)
   - decrypting the message --- gpg --decrypt <filename>
   - --> it uses your own private key to decrypt the message and uses public key in your keyring to identify the sender. You can be sure that the message came from alice and it was not altered on it's way
   

### f) Password management. 
Demonstrate use of a password manager. What kind of attacks take advantage of people not using password managers? (You can use any password manager, some examples include pass and KeePassXC.)
Password management
Using pass in my new best friend VM linux
1. install the password manager pass for ubuntu/debian
2. created my own password storage for
 $ pass init "pendfin Password Storage Key" 
 mkdir: created directory '/home/perttus/.password-store/' 
 Password store initialized for pendfin Password Storage Key 
3. Created new key pair for user that owns the password storage
     Real name: pendfin Password Storage Key
     Email address: 
     You selected this USER-ID:
     "pendfin Password Storage Key"
     pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
     01D752B1050E09A37A2DD524545DCCE773E8214B
     uid                      pendfin Password Storage Key
     sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]
     $ pass insert business/home-alone-2
     Enter password for business/home-alone-2: 
     Retype password for business/home-alone-2:
4. now i have a storage in my passworfd storage for business
5. I'll create passwords for my hobby
   $ pass generate hobby/catchmeifyoucan
   mkdir: created directory '/home/perttus/.password-store/hobby'
   The generated password for hobby/catchmeifyoucan is:
   SFHWk`a'kP2;>Jd!($ZU9!i.i
6. now it looks like this

      Password Store
    
      └── hobby
  
        └── catchmeifyoucan
 8. you can easily copy it clipboard which clears itself in 45 seconds, tested and worked

#### And why you should have this kind of keep?
 It is not possible (for most of us though) to remember all passwords for all different applications, webshops, stores etc.
 If you want them to be unique. Many people solve this to have one or two superior passwords. 
 Attacks using already leaked user+password data. you probably use your credentials somewhere else too
 Attack using human logic like 123 or sdfgh. Password managers can suggest random passwords which are not human like.
 If the service provider you're using (eshop or app) you loose just one account, because with password mangers you can keep different ones in everywhere. So it doest provide you some protection against brute force attacks, if you let the password manager create the passwords.
 In password manager your password is not kept in plaintext. So even your device is robbed a thief cannot get out. 
 One type of malice is to ask your password. If you keep it in your mind, you might just give by clicking the link and going to website (fake of course). With manager it might just recognise that there is something wrong with the webpage.
 Managers also prevent keystroke logging, because you don't have to type it, even there is camera or keystroke-logger installed on your computer you're safe.
 Sniffing is also prevented, because password doesn't travel through your network

Sources: 
 https://www.doherty.co.uk/blog/the-benefits-of-a-password-manager/ 
 
 https://www.passwordstore.org/ 
 
 https://www.ncsc.gov.uk/collection/top-tips-for-staying-secure-online/password-managers 
 
 Joe Kissell,2024,  Take Control of Your Passwords, 4th Edition, Published by Take Control Books, https://learning.oreilly.com/library/view/take-control-of/9781492066408/
 
p### g) Refer to sources. 
DONE

