# SHC-3.8.9b 
### [Francisco Javier Rosales García](https://www.datsi.fi.upm.es/~frosal/)

## How to use SHC Bash Script Compiler
- Option 1
### Command:
- git clone https://github.com/chris1111/SHC-3.8.9b.git
- cd $HOME/SHC-3.8.9b
- make


### Create /bin directory in /usr/local 
- sudo mkdir -p /usr/local/bin)
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

Below is a example for how to use it.
Create a .sh script at $HOME directory eg, name Myscript.sh

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

## How to use SHC Bash Script Compiler
- Option 2

Note: - The software used here is a copyright software which is available free to use. There is no code written by me. This document is only meant to help for how to use this software and create a binary of bash script. Any suggestions regarding the software can be directly send at frosal@fi.upm.es 


 
