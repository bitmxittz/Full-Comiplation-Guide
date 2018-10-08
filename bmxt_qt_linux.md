### Compile QT wallet on Linux

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


