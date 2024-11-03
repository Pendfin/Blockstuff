#### messaging (sunday 3.11.)
sudo apt-get update
Get:1 http://deb.debian.org/debian bookworm InRelease [151 kB]                      
Get:2 http://security.debian.org/debian-security bookworm-security InRelease [48,0 kB]
Get:3 http://deb.debian.org/debian bookworm-updates InRelease [55,4 kB]
Get:4 http://deb.debian.org/debian bookworm-backports InRelease [59,0 kB]
Get:5 http://security.debian.org/debian-security bookworm-security/main Sources [126 kB]
Get:6 http://security.debian.org/debian-security bookworm-security/main amd64 Packages [190 kB]
Get:7 http://security.debian.org/debian-security bookworm-security/main Translation-en [116 kB]
Get:8 http://deb.debian.org/debian bookworm-backports/main Sources.diff/Index [63,3 kB]
Get:9 http://deb.debian.org/debian bookworm-backports/main amd64 Packages.diff/Index [63,3 kB]
Get:10 http://deb.debian.org/debian bookworm-backports/main Translation-en.diff/Index [63,3 kB]
Get:11 http://deb.debian.org/debian bookworm-backports/main Sources T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [9 007 B]
Get:12 http://deb.debian.org/debian bookworm-backports/main amd64 Packages T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [11,3 kB]
Get:11 http://deb.debian.org/debian bookworm-backports/main Sources T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [9 007 B]
Get:12 http://deb.debian.org/debian bookworm-backports/main amd64 Packages T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [11,3 kB]
Get:13 http://deb.debian.org/debian bookworm-backports/main Translation-en T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [2 542 B]
Get:13 http://deb.debian.org/debian bookworm-backports/main Translation-en T-2024-11-02-2033.42-F-2024-10-26-2007.03.pdiff [2 542 B]
Fetched 958 kB in 6s (164 kB/s) 
sudo apt-get install gpg micro psmisc
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
gpg is already the newest version (2.2.40-1.1).
gpg set to manually installed.
psmisc is already the newest version (23.6-1).
psmisc set to manually installed.
The following additional packages will be installed:
  xclip
The following NEW packages will be installed:
  micro xclip
0 upgraded, 2 newly installed, 0 to remove and 70 not upgraded.
Need to get 3 723 kB of archives.
After this operation, 12,8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://deb.debian.org/debian bookworm/main amd64 micro amd64 2.0.11-2+b1 [3 700 kB]
Get:2 http://deb.debian.org/debian bookworm/main amd64 xclip amd64 0.13-2 [23,3 kB]
Fetched 3 723 kB in 5s (794 kB/s)
Selecting previously unselected package micro.
(Reading database ... 232687 files and directories currently installed.)
Preparing to unpack .../micro_2.0.11-2+b1_amd64.deb ...
Unpacking micro (2.0.11-2+b1) ...
Selecting previously unselected package xclip.
Preparing to unpack .../xclip_0.13-2_amd64.deb ...
Unpacking xclip (0.13-2) ...
Setting up micro (2.0.11-2+b1) ...
Setting up xclip (0.13-2) ...
Processing triggers for desktop-file-utils (0.26-1) ...
Processing triggers for man-db (2.11.2-2) ...
Processing triggers for mailcap (3.70+nmu1) ...
$ gpg --gen-key
gpg (GnuPG) 2.2.40; Copyright (C) 2022 g10 Code GmbH
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

gpg: keybox '/home/perttus/.gnupg/pubring.kbx' created
Note: Use "gpg --full-generate-key" for a full featured key generation dialog.

GnuPG needs to construct a user ID to identify your key.

Real name: Perttu Salo DEMO KEY
Email address: perttus@example.com.invalid
You selected this USER-ID:
    "Perttu Salo DEMO KEY <perttus@example.com.invalid>"

Change (N)ame, (E)mail, or (O)kay/(Q)uit? o
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: /home/perttus/.gnupg/trustdb.gpg: trustdb created
gpg: directory '/home/perttus/.gnupg/openpgp-revocs.d' created
gpg: revocation certificate stored as '/home/perttus/.gnupg/openpgp-revocs.d/91993942A020FFE23C8C059D2FF2F238673C4805.rev'
public and secret key created and signed.

pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      91993942A020FFE23C8C059D2FF2F238673C4805
uid                      Perttu Salo DEMO KEY <perttus@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]
gpg --export --armor --output perttus.pub
head -4 perttus.pub
-----BEGIN PGP PUBLIC KEY BLOCK-----

mQGNBGcnTN8BDAC4r4jIB/2EVWBgwF34IyhsKBhHQ1t3BLEkQIwPwzUeIk9fkkEt
U20JGgurW7G4NIet5MWRl9PhfMACrYqPgBPs6ySCVoNEkUjWR/dLm1FHYHGLh9uy
$ mkdir alice/
$ chmod og-rwx alice/
$ cd alice/
/alice$ gpg --homedir . --fingerprint
gpg: keybox '/home/perttus/alice/pubring.kbx' created
gpg: /home/perttus/alice/trustdb.gpg: trustdb created
/alice$ gpg --homedir . --gen-key
gpg (GnuPG) 2.2.40; Copyright (C) 2022 g10 Code GmbH
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Note: Use "gpg --full-generate-key" for a full featured key generation dialog.

GnuPG needs to construct a user ID to identify your key.

Real name: Alice
Email address: alice@example.com.invalid
You selected this USER-ID:
    "Alice <alice@example.com.invalid>"

Change (N)ame, (E)mail, or (O)kay/(Q)uit? o
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: directory '/home/perttus/alice/openpgp-revocs.d' created
gpg: revocation certificate stored as '/home/perttus/alice/openpgp-revocs.d/C485C6614F41383852C247C3E3E928DD2BEEECE2.rev'
public and secret key created and signed.

pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      C485C6614F41383852C247C3E3E928DD2BEEECE2
uid                      Alice <alice@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03] 
alice$ gpg --homedir . --fingerprint
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: next trustdb check due at 2026-11-03
/home/perttus/alice/pubring.kbx
 
 -------------------------------
pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2
uid           [ultimate] Alice <alice@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]
$ cp -v perttus.pub alice/
'perttus.pub' -> 'alice/perttus.pub
/alice$ gpg --homedir . --import perttus.pub
gpg: key 2FF2F238673C4805: public key "Perttu Salo DEMO KEY <perttus@example.com.invalid>" imported
gpg: Total number processed: 1
gpg:               imported: 1
/home/perttus/alice/pubring.kbx

 -------------------------------
pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2
uid           [ultimate] Alice <alice@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]

pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      9199 3942 A020 FFE2 3C8C  059D 2FF2 F238 673C 4805
uid           [ unknown] Perttu Salo DEMO KEY <perttus@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]
alice$ gpg --homedir . --sign-key "9199 3942 A020 FFE2 3C8C  059D 2FF2 F238 673C 4805"

pub  rsa3072/2FF2F238673C4805
     created: 2024-11-03  expires: 2026-11-03  usage: SC  
     trust: unknown       validity: unknown
sub  rsa3072/E7E4FCB97163CB31
     created: 2024-11-03  expires: 2026-11-03  usage: E   
[ unknown] (1). Perttu Salo DEMO KEY <perttus@example.com.invalid>


pub  rsa3072/2FF2F238673C4805
     created: 2024-11-03  expires: 2026-11-03  usage: SC  
     trust: unknown       validity: unknown
 Primary key fingerprint: 9199 3942 A020 FFE2 3C8C  059D 2FF2 F238 673C 4805

     Perttu Salo DEMO KEY <perttus@example.com.invalid>

This key is due to expire on 2026-11-03.
Are you sure that you want to sign this key with your
key "Alice <alice@example.com.invalid>" (E3E928DD2BEEECE2)

Really sign? (y/N) y
/alice$ gpg --homedir . --fingerprint
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   1  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: depth: 1  valid:   1  signed:   0  trust: 1-, 0q, 0n, 0m, 0f, 0u
gpg: next trustdb check due at 2026-11-03
/home/perttus/alice/pubring.kbx

-------------------------------
pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2
uid           [ultimate] Alice <alice@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]

pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      9199 3942 A020 FFE2 3C8C  059D 2FF2 F238 673C 4805
uid           [  full  ] Perttu Salo DEMO KEY <perttus@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]
alice$ gpg --homedir . --export --armor --output alice.pub
cd
$ cp -v alice/alice.pub .
'alice/alice.pub' -> './alice.pub'
$ gpg --import alice.pub
gpg: key E3E928DD2BEEECE2: public key "Alice <alice@example.com.invalid>" imported
gpg: key 2FF2F238673C4805: "Perttu Salo DEMO KEY <perttus@example.com.invalid>" 1 new signature
gpg: Total number processed: 2
gpg:               imported: 1
gpg:         new signatures: 1
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: next trustdb check due at 2026-11-03
gpg --homedir . --fingerprint
gpg: WARNING: unsafe permissions on homedir '/home/perttus'
gpg: keybox '/home/perttus/pubring.kbx' created
gpg: /home/perttus/trustdb.gpg: trustdb created
$ gpg --fingerprint
/home/perttus/.gnupg/pubring.kbx
+--------------------------------
pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      9199 3942 A020 FFE2 3C8C  059D 2FF2 F238 673C 4805
uid           [ultimate] Perttu Salo DEMO KEY <perttus@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]

pub   rsa3072 2024-11-03 [SC] [expires: 2026-11-03]
      C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2
uid           [ unknown] Alice <alice@example.com.invalid>
sub   rsa3072 2024-11-03 [E] [expires: 2026-11-03]

$ gpg --sign-key "C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2"

pub  rsa3072/E3E928DD2BEEECE2
     created: 2024-11-03  expires: 2026-11-03  usage: SC  
     trust: unknown       validity: unknown
sub  rsa3072/6A402B36B55D24BC
     crea
     ted: 2024-11-03  expires: 2026-11-03  usage: E   
[ unknown] (1). Alice <alice@example.com.invalid>


pub  rsa3072/E3E928DD2BEEECE2
     created: 2024-11-03  expires: 2026-11-03  usage: SC  
     trust: unknown       validity: unknown
 Primary key fingerprint: C485 C661 4F41 3838 52C2  47C3 E3E9 28DD 2BEE ECE2

     Alice <alice@example.com.invalid>

This key is due to expire on 2026-11-03.
Are you sure that you want to sign this key with your
key "Perttu Salo DEMO KEY <perttus@example.com.invalid>" (2FF2F238673C4805)

Really sign? (y/N) y
alice$ micro message.txt
alice$ gpg --homedir . --encrypt --recipient perttus@example.com.invalid --sign --output encrypted.pgp --armor message.txt
/alice$ ls encrypted.pgp
encrypted.pgp
alice$ head -4 encrypted.pgp
-----BEGIN PGP MESSAGE-----

hQGMA+fk/LlxY8sxAQwAsn44/b+mzZP1a3nk7Tv+62n5eMeU9hawaqk6zYzP/Eck
ZOeRu1J3VR1tnFAQ8UCB2mHK1lavWSOIJjJ5oCN3toMEfhLJRQqoWX4EBoq9ccip
/alice$ cd
~$ cp -v alice/encrypted.pgp .
'alice/encrypted.pgp' -> './encrypted.pgp'
$ gpg --decrypt encrypted.pgp
gpg: encrypted with 3072-bit RSA key, ID E7E4FCB97163CB31, created 2024-11-03
      "Perttu Salo DEMO KEY <perttus@example.com.invalid>"
Hi Perttus

This is my try-out to establish a secret connection with you.
Hope it goes well.
Alice
gpg: Signature made su  3. marraskuuta 2024 13.08.28 EET
gpg:                using RSA key C485C6614F41383852C247C3E3E928DD2BEEECE2
gpg: Good signature from "Alice <alice@example.com.invalid>" [full]
$ micro message2.txt
$ gpg --encrypt --recipient alice@example.com.invalid --sign --output encrypted2.pgp --armor message2.txt
$ head -4 encrypted2.pgp
-----BEGIN PGP MESSAGE-----

hQGMA2pAKza1XSS8AQwAj0woGTVP1lMspEI6vwpA8DZ5XES79MZnWfNnyR6lZiBm
VTdVFPlC8M4vu0DGHsbKijuN0gfMaq78aPA+cHZaD+ZfgXxaSnPpHRCRtGRIU/B2
$ cp -v encrypted2.pgp alice/
'encrypted2.pgp' -> 'alice/encrypted2.pgp'
/alice$ gpg --homedir . --decrypt encrypted2.pgp
gpg: encrypted with 3072-bit RSA key, ID 6A402B36B55D24BC, created 2024-11-03
      "Alice <alice@example.com.invalid>"
Hi Alice
This is my respond
NO
gpg: Signature made su  3. marraskuuta 2024 13.17.39 EET
gpg:                using RSA key 91993942A020FFE23C8C059D2FF2F238673C4805
gpg: Good signature from "Perttu Salo DEMO KEY <perttus@example.com.invalid>" [full]
