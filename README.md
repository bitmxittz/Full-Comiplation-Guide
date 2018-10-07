# Full-Comiplation-Guide

Bitmxittz BMXT wallet full compilation guide for windows and linux

Wallet Compilation
------------------

### Compile Daemon on Linux

use "sudo" before command line if you are not root user

update:

    apt-get update

upgrade:

    apt-get upgrade

make swapfile if low RAM:

    dd if=/dev/zero of=/swapfile bs=1024 count=1024288

edit fstab:

    nano /etc/fstab
    
Or use vim to edit

    vim /etc/fstab

Add this at the bottom of /etc/fstab:

    /swapfile none swap sw 0 0

To edit, press "Insert" if you using vim

To save and exit, if using nano press "cntr+O" then "cntl+x", if using vim press "Esc" type ":wq" hit "Enter"

command line:

    apt-get install ntp unzip git build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev libqrencode-dev aptitude && aptitude install miniupnpc libminiupnpc-dev

clone git src:

    git clone https://github.com/bitmxittz/Bitmxittz

enter leveldb:

    cd Bitmxittz/src/leveldb

grant permission:

    chmod 0755 build_detect_platform

make clean:

    make clean

make leveldb:

    make libleveldb.a libmemenv.a

home:

    cd

enter src:

    cd Bitmxittz/src

make clean:

    make -f makefile.unix clean

compile bitmxittzd static:

    make STATIC=1 -f makefile.unix bitmxittzd  

or compile bitmxittzd non-static:

    make -f makefile.unix bitmxittzd

trim bitmxittzd:

    strip bitmxittzd

copy bitmxittzd:

    cp bitmxittzd /usr/bin

start bitmxittzd and enter .bitmxittz:

    bitmxittzd & cd ~/.bitmxittz

edit bitmxittz configuration file:

    nano bitmxittz.conf 

or use vim to edit

    vim bitmxittz.conf

add following lines to bitmxittz.conf, change YOUR_RPC_USERNAME and YOUR_STRONG_PASSWORD with your own:

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

home:

    cd

start bitmxittz server:

    bitmxittzd

getinfo:

    bitmxittzd getinfo

getpeerinfo:

    bitmxittzd getpeerinfo


### Compile QT wallet on Linux


### Compile Daemon on Windows


### Compile QT wallet on Windows

