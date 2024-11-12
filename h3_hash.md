# h3 hashing
Source of these excercises is https://terokarvinen.com/trust-to-blockchain/#homework
## x) Read and summarize
###  2.3.One-way Fuctions 2.4 One-Way Hash Functions
- one-way function is a function that works one way. Easy from source to target, hard or almost impossible other way around
- one-way function can be used to encryption
- trap door one way function gives you means to crack the function also into two way-function
- one-way hash function is a function that takes what ever size input string and converts it fixed (depends of function) length string which is called hash value
- it is basically a fingerprint of that string (also called pre-image)
- hash function being collision free means that there should not be two different pre-images with same hash
- Message authentication code (MAC or DAC) is hash function with the key to verify the hash created of pre-image
Source: Schneier, B. 2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. New York: Wiley.
### Cracking passwords with Hashcat
- Hashcat is a program or a tool find or crack the hashes
- you use it with a dictionary with words e.g. possible passwords
- you choose the most propable hash type and run the program against hash id (the hash you try to crack)
- results is either cracked or failedmkdir hashed
Source: Karvinen 2022: Cracking Passwords with Hashcat (https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)
### Command line basics
- list of basic commands you need when using linux
- gives you hands on examples of how to create files, directories and how to manipulate and delete those
- it also shows how to connect via ssh to another computer
- and some tips when to use tabs, pipes and administrative commands
Source: Karvinen 2020: Command Line Basics Revisited (https://terokarvinen.com/2020/command-line-basics-revisited/)
€ Santos et al 2017
### a) Billion dollar busywork
Command 'echo -n "hello"|sha256sum' prints a hash. Try adding something to the string, e.g. 'echo -n 'hello asdf'|sha256sum'. What do you have to add to get a hash that starts with a zero? (Voluntary bonus: How is this related to Bitcoin? Voluntary difficult bonus: How many zeros can you get to the beginning? Voluntary difficult bonus: How does the difficulty raise?)
- first put something stupid like hellokello-->$ echo -n "hellokello"|sha256sum.This results 008a8ab2f87506883da9a9c907112a3c44198244a0acfb4b011a0033e93ef536--> actually two zeroes
- this is related to bitcoin? It is used to authenticate the transactions - so you can trust that those are not altered

### b) Compare hash
Compare hash. Create a small text file. Take it's hash (e.g. 'sha256sum tero.txt'). Change one letter. Take the hash again. Compare hashes. What do you notice?
- $ micro haskoe.txt--> create text file with micro
- $ write teini-ikäisetmutanttininjakilpikonnat
- $ sha256sum hashkoe.txt -->1524fb5595c18d49eca4c467928f8a256871240f95cb620fba02bf875c8a250e
- $micro hashkoe.txt--> change the file
- $ write teini-ikäisetmutanttininjakilpikonnat2
- $ sha256sum hashkoe.txt -->90f535b5ffa6e302e1b2c3dbe333301ccfb95a2865d0086b565be8a1ecfdecfb
- comparison
1524fb5595c18d49eca4c467928f8a256871240f95cb620fba02bf875c8a250e
90f535b5ffa6e302e1b2c3dbe333301ccfb95a2865d0086b565be8a1ecfdecfb
- almost everything changed - I cannot detect has one, two or all the letters changed
- hash is the same length as it should always be
Help with commands Karvinen 2020: Command Line Basics Revisited (https://terokarvinen.com/2020/command-line-basics-revisited/)

### c) Hashcat
Source: Karvinen 2022: Cracking Passwords with Hashcat (https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)
- create directory for play --> $ cd hashed
- download hashcat -->hashed$ wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
- unpack it -->hashed$ tar xf rockyou.txt.tar.gz
- check the contents --> hashed$ head rockyou.txt --> this displays first 10 rows of rockyou.txt
- and it seems ok, containing possible passwords 
- ready to rock it with hashcat, so testing it next
- taking my previous excersises hash--> hashed$ hashid -m 1524fb5595c18d49eca4c467928f8a256871240f95cb620fba02bf875c8a250e
- seems pretty good
- Analyzing '1524fb5595c18d49eca4c467928f8a256871240f95cb620fba02bf875c8a250e'
[+] Snefru-256 
[+] SHA-256 [Hashcat Mode: 1400]
[+] RIPEMD-256 
[+] Haval-256 
[+] GOST R 34.11-94 [Hashcat Mode: 6900]
[+] GOST CryptoPro S-Box 
[+] SHA3-256 [Hashcat Mode: 5000]
[+] Skein-256 
[+] Skein-512(256) 
-  using sha-256 (which i used in creating hash in excersie b) -->hashed$ hashcat -m 1400 '1524fb5595c18d49eca4c467928f8a256871240f95cb620fba02bf875c8a250e' rockyou.txt -o testipurku
-  And this will take some time with virtual machine..........
-Exhausted ,Started: Tue Nov 12 17:46:19 2024,Stopped: Tue Nov 12 17:49:09 2024
- no match, of course, the text was pretty good and not in the file rockyou.txt
- so it's working, no file was createdcat

### d) Dictionary attack.
Source: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/
- first, find out what kind of hash is this 21232f297a57a5a743894a0e4a801fc3?
Analyzing '21232f297a57a5a743894a0e4a801fc3'
[+] MD2 
[+] MD5 [Hashcat Mode: 0]
[+] MD4 [Hashcat Mode: 900]
[+] Double MD5 [Hashcat Mode: 2600]
[+] LM [Hashcat Mode: 3000]
[+] RIPEMD-128 
[+] Haval-128 
[+] Tiger-128 
[+] Skein-256(128) 
[+] Skein-512(128) 
[+] Lotus Notes/Domino 5 [Hashcat Mode: 8600]
[+] Skype [Hashcat Mode: 23]
[+] Snefru-128 
[+] NTLM [Hashcat Mode: 1000]
[+] Domain Cached Credentials [Hashcat Mode: 1100]
[+] Domain Cached Credentials 2 [Hashcat Mode: 2100]
[+] DNSSEC(NSEC3) [Hashcat Mode: 8300]
[+] RAdmin v2.x [Hashcat Mode: 9900]
- what should I choose? I take MD5, because the guide recommends it to be common
- try to crack it--> hashcat -m 0 '21232f297a57a5a743894a0e4a801fc3' rockyou.txt -o ratkaisu1
- the solution in file ratkaisu1 --> hashed$ cat ratkaisu1
- 21232f297a57a5a743894a0e4a801fc3:admin
- doesn't seem so unique to me - cracked

### e) How can you make a password that's protected against a dictionary attack?
- you can create your own long password with uniquenes
- you can use passphrase which might be something personal or in finnish or savo
- you can use Salt, a way to complicate the hashes created from the passwords and stored in password file
  - but it only makes cracking harder, not impossible because it adds a string before using the one-way function
- and finally you can't, there is always a tiny small possibility that someone will crack it    
- Source: Schneier, B. 2015. Chapter 3 Basic protocols and chapter 8 Key management, Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. New York: Wiley 
### f) Voluntary: Two minute job
- idenitfying what kind of hash this is --> hashed$ hashid -m '$2y$18$axMtQ4N8j/NQVItQJed9uORfsUK667RAWfycwFMtDBD6zAo1Se2eu'
- Analyzing '$2y$18$axMtQ4N8j/NQVItQJed9uORfsUK667RAWfycwFMtDBD6zAo1Se2eu'
[+] Blowfish(OpenBSD) [Hashcat Mode: 3200]
[+] Woltlab Burning Board 4.x 
[+] bcrypt [Hashcat Mode: 3200]
- running with 3200 and rockypuo file -->hashed$ hashcat -m 3200 '$2y$18$axMtQ4N8j/NQVItQJed9uORfsUK667RAWfycwFMtDBD6zAo1Se2eu' rockyou.txt -o ratkaisu2
- with rockyou i found find the solution--> $2y$18$axMtQ4N8j/NQVItQJed9uORfsUK667RAWfycwFMtDBD6zAo1Se2eu:12345
- pure luck? some warnings while cracking -to update or use parallellization but it worked

### g) Voluntary bonus: Where do you want to go today?
- finding parameters for hash ewith hashid --> hashed$ hashid -m f2477a144dff4f216ab81f2ac3e3207d
- Windows NTLM? it seems to be [+] NTLM [Hashcat Mode: 1000]
- try to crack it --> /hashed$ hashcat -m 1000 'f2477a144dff4f216ab81f2ac3e3207d' rockyou.txt -o ratkaisu3
- cracked-->hashed$ cat ratkaisu3
- f2477a144dff4f216ab81f2ac3e3207d:monkey--> this doesn't seem to be answer to the question? did I use so
### h) Voluntary bonus: Embarassingly parallel
- skipping this

### i) my hash
- skipping this
### j) John. Install Jumbo
Source; https://terokarvinen.com/2023/crack-file-password-with-john/
- Installing with instructions, skipping micro because it is already installed--> hashed$ $ sudo apt-get -y install bash-completion git build-essential libssl-dev zlib1g zlib1g-dev zlib-gst libbz2-1.0 libbz2-dev atool zip wge
- downloading it --> hashed$ git clone --depth=1 https://github.com/openwall/john.git
- making the directory and creating makefile
- one error missing openssl (trying to install it, didn't work) -->  sudo apt-get -y install openssl
- continuing to compile--> no make can do---> deleting all files and starting over again in main directory
- doesn't find the file packages E: Unable to locate package zlib-gst
- trying to upgrade packages with sudo apt-upgrade
- finding out is there actually different packages for zip--> $ sudo apt-get -y install zziplib-bin
- cloning john again and creating folders
- some kind of success
  Configured for building John the Ripper jumbo:

Target CPU ......................................... x86_64 AVX2, 64-bit LE
AES-NI support ..................................... depends on OpenSSL
Target OS .......................................... linux-gnu
Cross compiling .................................... no
Legacy arch header ................................. x86-64.h

Optional libraries/features found:
Memory map (share/page large files) ................ yes
Fork support ....................................... yes
OpenMP support ..................................... yes (not for fast formats)
OpenCL support ..................................... no
Generic crypt(3) format ............................ yes
OpenSSL (many additional formats) .................. yes
libgmp (PRINCE mode and faster SRP formats) ........ no
128-bit integer (faster PRINCE mode) ............... yes
libz (7z, pkzip and some other formats) ............ yes
libbz2 (7z and gpg2john bz2 support) ............... yes
libpcap (vncpcap2john and SIPdump) ................. no
Non-free unrar code (complete RAR support) ......... yes
librexgen (regex mode, see doc/README.librexgen) ... no
OpenMPI support (default disabled) ................. no
Experimental code (default disabled) ............... no
ZTEX USB-FPGA module 1.15y support ................. no

Install missing libraries to get any needed features that were omitted.

Configure finished.  Now "make -s clean && make -sj1" to compile.
- make -s clean && make -sj4 (because instruction said to use -sj4)
- Took a while and fan was screaming--> process completed
- lots of stuff in /john/run$ ls -1
1password2john.py
7z2john.pl
adxcsouf2john.py
- and running it $HOME/john/run/john--> John the Ripper 1.9.0-jumbo-1+bleeding-b86611a49b 2024-11-12 01:11:22 +0100 OMP [linux-gnu 64-bit x86_64 AVX2 AC]
  
### k) Crack file password with John
Source: https://terokarvinen.com/2023/crack-file-password-with-john/
- Getting the file to crack wget https://TeroKarvinen.com/2023/crack-file-password-with-john/tero.zip
- Trying to unzip it - doesn't work
- Calling John to help me and create me a hash --> $HOME/john/run/zip2john tero.zip >tero.zip.hash
- CheckinK tero.zip.hash exists - yes it does
- running John with Tero and attack -->$HOME/john/run/john tero.zip.hash
- success: password was found
- sing default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Warning: OpenMP is disabled; a non-OpenMP build may be faster
Note: Passwords longer than 21 [worst case UTF-8] to 63 [ASCII] rejected
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, 'h' for help, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
0g 0:00:00:00 DONE 1/3 (2024-11-12 20:09) 0g/s 444773p/s 444773c/s 444773C/s Mdzip1900..Msecret1900
Proceeding with wordlist:/home/perttus/john/run/password.lst
Enabling duplicate candidate password suppressor
butterfly        (tero.zip/secretFiles/SECRET.md)     
1g 0:00:00:00 DONE 2/3 (2024-11-12 20:09) 3.226g/s 276938p/s 276938c/s 276938C/s butterfly..december
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
- unzip the file and....
- You've found the secret, well done!
You have now completed the tutorial. 
Did you know that Jumbo John can handle many other file formats, too [1]?
[1] https://TeroKarvinen.com/2023/crack-file-password-with-john/



