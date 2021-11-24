# SHC-3.8.9b 
### Original Author ➤ [Francisco Javier Rosales García](https://www.datsi.fi.upm.es/~frosal/)

## How to use SHC Bash Script Compiler on macOS (Two ways available to you)

### You need install Command Line tools

- Option 1
### Command:
- git clone https://github.com/chris1111/SHC-3.8.9b.git
- cd $HOME/SHC-3.8.9b
- make


### Create /bin directory in /usr/local 
- sudo mkdir -p /usr/local/bin
### copy shc binary to /usr/local/bin 
- sudo cp -R $HOME/SHC-3.8.9b/shc /usr/local/bin
### give execute permissions 
- chmod +x /usr/local/bin/shc

- shc -h
This will give you all the options of the command.

shc Copyright (c) 1994-2003 Francisco Rosales <frosal@fi.upm.es>
shc Usage: shc [-e date] [-m addr] [-i iopt] [-x cmnd] [-l lopt] [-rvDTCAh] -f script

    -e %s  Expiration date in dd/mm/yyyy format [none]
    -m %s  Message to display upon expiration ["Please contact your provider"]
    -f %s  File name of the script to compile
    -i %s  Inline option for the shell interpreter i.e: -e
    -x %s  eXec command, as a printf format i.e: exec('%s',@ARGV);
    -l %s  Last shell option i.e: --
    -r     Relax security. Make a redistributable binary
    -v     Verbose compilation
    -D     Switch ON debug exec calls [OFF]
    -T     Allow binary to be traceable [no]
    -C     Display license and exit
    -A     Display abstract and exit
    -h     Display help and exit

    Environment variables used:
    Name    Default  Usage
    CC      cc       C compiler command
    CFLAGS  <none>   C compiler flags

    Please consult the shc(1) man page.
#### [shc Readme](https://github.com/chris1111/SHC-3.8.9b/blob/main/shc.README)
#### [Man Page](https://www.datsi.fi.upm.es/~frosal/sources/shc.html)

Below is a example for how to use it.
Create a .sh script at $HOME directory eg, name Myscript.sh

### Command:
- shc -v -r -T -f Myscript.sh


This will create 2 file as output;
Myscript.sh.x
Myscript.sh.x.c

### We just have to rename the ".x"  file as some name.
e.g.
- mv Myscript.sh.x Myscript
### This will create a binary "Myscript", which we will give execute permission and use.
- chmod +x Myscript
- sudo mkdir -p /usr/local/bin
- sudo cp -Rp Myscript /usr/local/bin

Now we can use it directly.
#Myscript


<img width="941" alt="Screen Shot" src="https://user-images.githubusercontent.com/6248794/143290784-d0406887-6f87-4fb9-9b82-01a2b371bf46.png">

## How to use SHC Bash Script Compiler (Option 2)
- Option 2
### Command:
- git clone https://github.com/chris1111/SHC-3.8.9b.git
- cd $HOME/SHC-3.8.9b
- make

Below is a example for how to use it.
Create a .sh script at $HOME/SHC-3.8.9b directory eg, name Myscript.sh

### Command:
- cd $HOME/SHC-3.8.9b
- shc -f *.sh
- ls -l  *.sh*
- file  *.sh
- file  *.sh.x
- file  *.sh.x.c
- shc -v -r -T -f *.sh



This will create 2 file as output; in directory $HOME/SHC-3.8.9b
Myscript.sh.x
Myscript.sh.x.c

### We just have to rename the ".x"  file as some name.
Myscript.sh.x to Myscript then double clic on it. This file is a Crypted Script.
- Note Myscript.sh.x.c can be use in an Xcode Command Line project (Myscript.c) ➤[See Project](https://github.com/chris1111/CloverBootloader-Git/commit/d29fbbec095a0a7f9db0789fb6de42586cd28537)

![SHC](https://user-images.githubusercontent.com/6248794/143289157-2da4f023-aa34-45d2-925c-c9c457521852.png)


<details>
    <summary>See result</summary>


```
Last login: Wed Nov 24 12:08:07 on ttys000
chris@iMac-de-chris ~ % git clone https://github.com/chris1111/SHC-3.8.9b.git
Cloning into 'SHC-3.8.9b'...
remote: Enumerating objects: 39, done.
remote: Counting objects: 100% (39/39), done.
remote: Compressing objects: 100% (30/30), done.
remote: Total 39 (delta 14), reused 32 (delta 7), pack-reused 0
Receiving objects: 100% (39/39), 25.82 KiB | 2.58 MiB/s, done.
Resolving deltas: 100% (14/14), done.
chris@iMac-de-chris ~ % cd $HOME/SHC-3.8.9b
chris@iMac-de-chris SHC-3.8.9b % make
cc -Wall  shc.c -o shc
***	?Do you want to probe shc with a test script?
***	Please try...	make test
chris@iMac-de-chris SHC-3.8.9b % shc -f *.sh
Myscript.sh.x.c:337:19: warning: 'ePtAttachDeprecated' is deprecated: PT_ATTACH is deprecated. See PT_ATTACHEXC [-Wdeprecated-declarations]
                        mine = !ptrace(PTRACE_ATTACH, pid, 0, 0);
                                       ^
Myscript.sh.x.c:318:24: note: expanded from macro 'PTRACE_ATTACH'
#define PTRACE_ATTACH    PT_ATTACH
                                ^
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/sys/ptrace.h:86:25: note: expanded from macro 'PT_ATTACH'
#define PT_ATTACH       ePtAttachDeprecated     /* trace some running process */
                        ^
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/sys/ptrace.h:72:22: note: 'ePtAttachDeprecated' has been explicitly marked deprecated here
        ePtAttachDeprecated __deprecated_enum_msg("PT_ATTACH is deprecated. See PT_ATTACHEXC") = 10
                            ^
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/sys/cdefs.h:214:38: note: expanded from macro '__deprecated_enum_msg'
        #define __deprecated_enum_msg(_msg) __deprecated_msg(_msg)
                                            ^
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/sys/cdefs.h:208:48: note: expanded from macro '__deprecated_msg'
        #define __deprecated_msg(_msg) __attribute__((__deprecated__(_msg)))
                                                      ^
1 warning generated.
chris@iMac-de-chris SHC-3.8.9b % ls -l  *.sh*
-rwxr-xr-x@ 1 chris  staff    902 23 Nov 13:40 Myscript.sh
-rwx--x--x  1 chris  staff  51072 24 Nov 12:13 Myscript.sh.x
-rw-r--r--  1 chris  staff  14300 24 Nov 12:13 Myscript.sh.x.c
-rwxr-xr-x  1 chris  staff    155 24 Nov 12:12 pru.sh
chris@iMac-de-chris SHC-3.8.9b % file  *.sh
Myscript.sh: POSIX shell script text executable, ASCII text
pru.sh:      POSIX shell script text executable, ASCII text
chris@iMac-de-chris SHC-3.8.9b % file  *.sh.x
Myscript.sh.x: Mach-O 64-bit executable x86_64
chris@iMac-de-chris SHC-3.8.9b % file  *.sh.x.c
Myscript.sh.x.c: ASCII text
chris@iMac-de-chris SHC-3.8.9b % shc -v -r -T -f *.sh
shc shll=sh
shc [-i]=-c
shc [-x]=exec '%s' "$@"
shc [-l]=
shc opts=
shc: cc  Myscript.sh.x.c -o Myscript.sh.x
shc: strip Myscript.sh.x
shc: chmod go-r Myscript.sh.x
chris@iMac-de-chris SHC-3.8.9b % 

    




```
    
</details>


Note: - The software used here is a copyright software which is available free to use. There is no code written by me. This document is only meant to help for how to use this software and create a binary of bash script. Any suggestions regarding the software can be directly send at frosal@fi.upm.es 


 
