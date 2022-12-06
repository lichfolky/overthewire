```
 _                     _ _ _   
| |__   __ _ _ __   __| (_) |_ 
| '_ \ / _` | '_ \ / _` | | __|
| |_) | (_| | | | | (_| | | |_ 
|_.__/ \__,_|_| |_|\__,_|_|\__|
```

https://overthewire.org/wargames/bandit/

```
bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0
```
`ssh bandit0@bandit.labs.overthewire.org -p 2220`

`scp -P 2220 bandit0@bandit.labs.overthewire.org:readme test.md `

NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

`exit` to exit

## Lv 1

commands: ls , cd , cat , file , du , find

`cat < -`
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi


## Lv 2

`cat spaces\ in\ this\ filename` 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Lv 3
```
cd inhere/
cat .hidden
```

2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Lv 4
`find . -type f` not worked 
`cat ./*`
MtlrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
`cat -- -file07`
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Lv 5 
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
```
human-readable
1033 bytes in size
not executable
```
`ls -Ral` no

`find . -type f -size +4096c`

b – 512-byte blocks (this is the default if no suffix is used)
c – bytes
w – two-byte words
k – Kilobytes
M – Megabytes
G – Gigabytes

`find . -type f -size 1033c`

P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Lv 6

```
The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size
```
cd ..

find . -size 33c -user bandit7 -group bandit6
```
./var/lib/dpkg/info/bandit7.password
```
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Lv 7

The password for the next level is stored in the file data.txt next to the word millionth

grep -inRsH "millionth"  /path/to/dir (it can be '.')
grep -inRsH "millionth"  /path/to/dir (it can be '.')

i stands for ignore case distinctions
R stands for recursive and it also include symlinks. It is better to use 'R' instead of 'r'
n stands for "it will print line number".
s stands for "suppress error messages"
H stands for "it will print the file name for each match"

`grep "millionth" data.txt`

millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Lv 8

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once


grep 'patten1' *.txt | grep 'pattern2' 

grep '' data.txt | grep -c ''

`sort data.txt | uniq -c`
`sort data.txt | uniq --count | sort`

EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## LV 9
You can use ^ and $ to force a regex to match only at the start or end of a line

grep --text

`grep --text "===." data.txt` 
/}f��Ӡ�:26=Ԑ���'�A�?�z۽bXK�!&v����M2�P�YA�����D�⊽��(���Zo�&{�s���b�b���a@��========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## LV 10

The password for the next level is stored in the file data.txt, which contains base64 encoded data
-e encode (default)
-d decode

`base64 -d data.txt`
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## LV 11
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

`cat data.txt | tr a-z A-Z`
GUR CNFFJBEQ VF WIAOOSFZMJXXBC0KOSKBBJ8PUQM5LIEI

`cat data.txt |tr [a-z] [n-za-m]`
Ghe password is WIAOOSFmMwXXBC0KbSKBoJ8chQz5yIEv

`cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]`
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

https://en.wikipedia.org/wiki/ROT13
https://medium.com/@piyush.kochhar1/rot13-a-missing-guide-c811427cfe6e

## LV 12 

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

 mkdir /tmp/lich
 cp data.txt /tmp/lich/data.txt


hexdump -C test.txt

xxd - make a hexdump or do the reverse.
xxd -r data.txt 
-r revert to binary
-r -p if no columns of the dump

`xxd image.jpg > image.txt`
`xxd -r data.txt > datar`


tar -xvzf documents.tar.gz

```
bzip2 -d data.txt
bzip2: Can't guess original name for data.txt -- using data.txt.out
bzip2: data.txt is not a bzip2 file.
```
```
file data
data: gzip compressed data, was "data2.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 575
```
gzip -d filename.gzcp 

cp data data.gz
gzip -d data.gz 

file data
data: bzip2 compressed data, block size = 900k
bzip2 -d data.txt

...

file datau
datau: POSIX tar archive (GNU)

tar -xvf <tar_archive> <filename>

file data5.bin
data5.bin: POSIX tar archive (GNU)

....


bandit12@bandit:/tmp/lich$ file data8
data8: ASCII text
bandit12@bandit:/tmp/lich$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

finally...

## LV 13
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

ssh -i ~/.ssh/old_keys/host2_key username@host2.somewhere.edu
ssh -i ~/.ssh/old_keys/host2_key username@host2.somewhere.edu

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0640 for 'sshkey.private' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "sshkey.private": bad permissions

ls -al
total 32
drwxr-xr-x   6 Lichfolky  staff   192 12 Nov 01:16 .
drwxr-xr-x  24 Lichfolky  staff   768 11 Nov 18:39 ..
drwxr-xr-x  14 Lichfolky  staff   448 11 Nov 23:10 .git
-rw-r--r--   1 Lichfolky  staff    88 11 Nov 19:07 README.md
-rw-r--r--   1 Lichfolky  staff  5743 12 Nov 01:18 bandit.md
-rw-r-----   1 Lichfolky  staff  1679 12 Nov 01:12 sshkey.private

`chmod 600  sshkey.private`


## LV 14
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

```
telnet localhost 30000
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## LV 15

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

```
openssl s_client -connect localhost:30001
...
    0060 - 2c 4c 9b b4 09 07 eb 78-e4 90 88 1d 32 1c f0 af   ,L.....x....2...
    0070 - 38 d5 66 65 66 17 b5 0a-cf dc be 79 4c 74 f3 2e   8.fef......yLt..
    0080 - 1f 7d 38 12 13 43 2d 04-48 63 d5 e7 d7 fd 95 17   .}8..C-.Hc......
    0090 - c8 eb 1f 1c ef 93 eb c1-89 2b 5f b8 83 26 3e b8   .........+_..&>.
    00a0 - 60 14 a0 95 13 05 ff 5e-34 2e 26 62 65 48 cc 5d   `......^4.&beH.]
    00b0 - aa 12 ef ce c4 81 4c de-46 ed 33 2d 1c 8a 2c c5   ......L.F.3-..,.
    00c0 - f9 65 0e e6 84 1c 85 d6-8f c5 61 3b 80 c9 a8 ba   .e........a;....

    Start Time: 1668214060
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
-----
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```
## Lv 16

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

ssh, telnet, nc, openssl, s_client, nmap

https://nmap.org/book/man.html

`nmap -p 31000-32000 localhost`
```
31046/tcp open     unknown
31518/tcp filtered unknown
31691/tcp open     unknown
31790/tcp open     unknown
31960/tcp open     unknown
```
`openssl s_client -connect localhost:31046`


-ign_eof

`echo -e "GET / HTTP/1.0\r\n" | openssl s_client -connect twitter.com:443 -CAfile PCA-3G5.pem -ign_eof`
`echo -e "JQttfApK4SeyHwDlI9SXGR50qclOAil1" | openssl s_client -connect localhost:31691 -ign_eof`

echo | openssl s_client -connect redhat.com:443
`echo | openssl s_client -connect localhost:31691`


https://it.linux-console.net/?p=1556#gsc.tab=0

for in connection
nc -z -v -w 2 192.168.56.1 31046 31518 31691 31790 31960

https://www.feistyduck.com/library/openssl-cookbook/online/


**Return** ssh bandit16@bandit.labs.overthewire.org -p 2220
JQttfApK4SeyHwDlI9SXGR50qclOAil1

`nmap -p 31000-32000 localhost`
```
31046/tcp open     unknown
31518/tcp filtered unknown
31691/tcp open     unknown
31790/tcp open     unknown
31960/tcp open     unknown
```
`openssl s_client -connect localhost:31518`  
no
`openssl s_client -connect localhost:31691`  
same res
`openssl s_client -connect localhost:31790`  
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed


to enter in Lv 17
`ssh -i sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220`
`chmod 600  sshkey17.private`


## Lv 17
https://overthewire.org/wargames/bandit/bandit18.html

`diff passwords.new passwords.old` 
```42c42
< hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
---
> U79zsNCl1urwJ5rU6pg7ZSCi7ifWOWpT
```


`hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg`

```
Byebye !
Connection to bandit.labs.overthewire.org closed.
```
## Lv 18
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.


```
 ssh bandit18@bandit.labs.overthewire.org -p 2220 bash --norc --noprofile
```
`awhqfNnAbc1naukrpqDYcF95h7HoMTrC`
 ## Lv 19


```
 ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
```

```
./bandit20-do cat /etc/bandit_pass/bandit20

VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

## Lv 20

https://overthewire.org/wargames/bandit/bandit21.html