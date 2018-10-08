### Compile And Run QT Wallet On Linux

use "sudo" before command line if you are not root user

update:

    apt-get update

upgrade:

    apt-get upgrade

swapfile for low RAM:

    dd if=/dev/zero of=/swapfile bs=1024 count=1024288

Add following line at the bottom of nano /etc/fstab: 

    /swapfile none swap sw 0 0

libs:

    apt-get install ntp unzip git build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev libqrencode-dev aptitude && aptitude install miniupnpc libminiupnpc-dev

clone src code:

git clone https://github.com/bitmxittz/Bitmxittz

enter leveldb:

    cd Bitmxittz/src/leveldb

grant file permission:

    chmod 0755 build_detect_platform

make clean:

    qmake clean

make libs:

    qmake libleveldb.a libmemenv.a

home:

    cd

enter bitmxittz folder:

    cd Bitmxittz

compile bitmxittz-qt without upnp:

    qmake USE_UPNP=-

or compile bitmxittz-qt with upnp:

    qmake USE_UPNP=-

make release:

    make

Your bitmxittz-qt wallet now available in folder C:\Bitmxittz\Release

Open bitmxittz-qt wallet then close it, now add following lines to bitmxittz.conf in datadir Bitmxittz folder or create one text editor save and exit, change YOUR_RPC_USERNAME and YOUR_STRONG_PASSWORD with your own:

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

restart bitmxittz-qt wallet

Done, your wallet will start synchronising with network now...

--------------------

## Download For Linux

bitmxittzd v1.0.0.1 https://mega.nz/#!BWxxVD7J!GOFYNhRbUCWury8mv0OC2H7CRBeWhUtvn-AF-ZCnm-U

bitmxittzd v1.0.0.2 https://mega.nz/#!BWxxVD7J!GOFYNhRbUCWury8mv0OC2H7CRBeWhUtvn-AF-ZCnm-U


## License
    
done, now you can open wallet configure bitmxittz.conf and run qt wallet on linux.

https://bitmxittz.com/license/

https://bitmxittz.mit-license.org/

