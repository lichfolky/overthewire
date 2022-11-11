# Bandit
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