# Full-Comiplation-Guide

Bitmxittz BMXT wallet full compilation guide for windows and linux

Wallet Compilation
------------------

### Compile Daemon on Linux

use "sudo" before command line if you are not root user

command line:

    apt-get update

command line:

    apt-get upgrade

If low on RAM

command line:

    dd if=/dev/zero of=/swapfile bs=1024 count=1024288

command line:

    nano /etc/fstab
    
Or use vim

command line:

    vim /etc/fstab

Add this at the bottom of /etc/fstab: /swapfile none swap sw 0 0

To edit, press "Insert" if you using vim

To save and exit, if using nano press "cntr+O" then "cntl+x", if using vim press "Esc" type ":wq" hit "Enter"

command line:

    apt-get install ntp unzip git build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev libqrencode-dev aptitude && aptitude install miniupnpc libminiupnpc-dev

command line:

    git clone https://github.com/bitmxittz/Bitmxittz

command line:

    cd Bitmxittz/src/leveldb

command line:

    chmod 0755 build_detect_platform

command line:

    make clean

command line:

    make libleveldb.a libmemenv.a

command line:

    cd

command line:

    cd Bitmxittz/src

command line:

    make -f makefile.unix clean

command line:

    make STATIC=1 -f makefile.unix bitmxittzd  

-or-  


command line:

    make -f makefile.unix bitmxittzd

command line:

    strip bitmxittzd

command line:

    cp bitmxittzd /usr/bin

command line:

    bitmxittzd & cd ~/.bitmxittz

command line:

    nano bitmxittz.conf 

or 

command line:

    vim bitmxittz.conf

Edit following lines, change YOUR_RPC_USERNAME and YOUR_STRONG_PASSWORD with your own

command line:

    rpcuser=YOUR_RPC_USERNAME
    rpcpassword=YOUR_STRONG_PASSWORD
    rpcallowip=127.0.0.1
    port=14433
    rpcport=14432
    daemon=1
    server=1
    listen=1
    testnet=0
    txindex=1
    timeout=30000
    rpctimeout=30000
    addnode=nd1.bitmxittz.com
    addnode=nd2.bitmxittz.com
    addnode=nd3.bitmxittz.com
    addnode=nd4.bitmxittz.com
    addnode=nd5.bitmxittz.com

if using nano cntr+O then cntl+x, if using vim Esc :wq Enter, to save and exit.

command line:

    cd

command line:

    bitmxittzd

command line:

    bitmxittzd getinfo

command line:

    bitmxittzd getpeerinfo


### Compile QT wallet on Linux


### Compile Daemon on Windows


### Compile QT wallet on Windows

