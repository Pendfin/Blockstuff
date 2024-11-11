# h3 hashing
Source of these excercises is https://terokarvinen.com/trust-to-blockchain/#homework
## x) Read and summarize
###  One-way Fuctions 2.4 One-Way Hash Functions
- 
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
- this is related to bitcoin?

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
- create directory for play cd hashed
- download hashcat
- unpack it
- check the contents
- ready to rock 

### d) Dictionary attack.

### e) How can you make a password that's protected against a dictionary attack?

### f) Voluntary: Two minute job

### g) Voluntary bonus: Where do you want to go today?

### h) Voluntary bonus: Embarassingly parallel

### j) John. Install Jumbo

### k) Crack file password with John

