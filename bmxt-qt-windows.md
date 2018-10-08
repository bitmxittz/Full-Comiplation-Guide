## Compile And Run Bitmxittz Qt Wallet On Linux

#### 1. Pre Installers

a. Winrar

b. Compression

c. MinGW

#### 2. Windows Deps

a. OpenSSL

b. Berkeley DB

c. Boost

d. MiniUPNP

e. Protoc and Libprotobuf

f. Libpng

g. qrencode

#### 3. Download and Compile QT

a. download and compile qt

b. compile bitmxittz qt wallet

---------------------------------------------------------------------------


#### 1. Pre Installers

1a. File Compressor/Extractor

Download and install Winrar or an alternate file compression tool. 

http://www.rarlab.com/download.htm


1b. Text Editor

Download and install a text editor such as Sublime Text.

http://www.sublimetext.com/


1c. Download and install MingW

http://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download

Double click to install, keep the checkbox for the GUI checked and make sure to install in C:\MinGW. Press continue. 

From the MinGW GUI interface, go to all packages -> MYSYS

Right click on the following installations and mark for installation.

msys-base-bin (may highlight other checkboxes which is fine)

msys-autoconf-bin

msys-automake-bin

msys-libtool-bin

Click on Installation -> Apply changes. MinGW will now download the remaining packages. Make sure to remove any previous installs of MinGW before starting. 

Once complete, navigate to C:\MinGW\bin and you should only have a mingw-get application. If you have msys-gcc and msys-w32api you need to delete MinGW and check the correct install packages are selected above.


Download and extract mingw32 to C:\mingw32

http://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/4.9.1/theads-posix/dwarf/i686-4.9.1-release-posix-dwarf-rt_v3-rev1.7z/download

You now need to change the path variables. Go to control panel->system and security->system. Click on advanced system properties->environmental variables. 

In the top box navigate to PATH and change to

code:

    C:\mingw32\bin;%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\
    
Checking your MingW install. To start the MingW app navigate to C:\MinGW\msys\1.0\msys.bat, create a desktop shortcut as you will use the msys command as well as the windows command prompts. 

Double click to start and enter the following to display the version and correct paths.

Code:

    gcc -v

Your msys output should look like the following code.

    $ gcc -v
    Using built-in specs.
    COLLECT_GCC=c:\mingw32\bin\gcc.exe
    COLLECT_LTO_WRAPPER=c:/mingw32/bin/../libexec/gcc/i686-w64-mingw32/4.9.1/lto-wrapper.exe
    Target: i686-w64-mingw32
    Configured with: ../../../src/gcc-4.9.1/configure --host=i686-w64-mingw32 --build=i686-w64-mingw32 --target=i686-w64-mingw32 --prefix=/
    mingw32 --with-sysroot=/c/mingw491/i686-491-posix-dwarf-rt_v3-rev1/mingw32 --with-gxx-include-dir=/mingw32/i686-w64-mingw32/include/c++
     --enable-shared --enable-static --disable-multilib --enable-languages=ada,c,c++,fortran,objc,obj-c++,lto --enable-libstdcxx-time=yes -
    -enable-threads=posix --enable-libgomp --enable-libatomic --enable-lto --enable-graphite --enable-checking=release --enable-fully-dynam
    ic-string --enable-version-specific-runtime-libs --disable-sjlj-exceptions --with-dwarf2 --disable-isl-version-check --disable-cloog-ve
    rsion-check --disable-libstdcxx-pch --disable-libstdcxx-debug --enable-bootstrap --disable-rpath --disable-win32-registry --disable-nls
     --disable-werror --disable-symvers --with-gnu-as --with-gnu-ld --with-arch=i686 --with-tune=generic --with-libiconv --with-system-zlib
     --with-gmp=/c/mingw491/prerequisites/i686-w64-mingw32-static --with-mpfr=/c/mingw491/prerequisites/i686-w64-mingw32-static --with-mpc=
    /c/mingw491/prerequisites/i686-w64-mingw32-static --with-isl=/c/mingw491/prerequisites/i686-w64-mingw32-static --with-cloog=/c/mingw491
    /prerequisites/i686-w64-mingw32-static --enable-cloog-backend=isl --with-pkgversion='i686-posix-dwarf-rev1, Built by MinGW-W64 project'
         --with-bugurl=http://sourceforge.net/projects/mingw-w64 CFLAGS='-O2 -pipe -I/c/mingw491/i686-491-posix-dwarf-rt_v3-rev1/mingw32/opt/in
    clude -I/c/mingw491/prerequisites/i686-zlib-static/include -I/c/mingw491/prerequisites/i686-w64-mingw32-static/include' CXXFLAGS='-O2 -
    pipe -I/c/mingw491/i686-491-posix-dwarf-rt_v3-rev1/mingw32/opt/include -I/c/mingw491/prerequisites/i686-zlib-static/include -I/c/mingw4
    91/prerequisites/i686-w64-mingw32-static/include' CPPFLAGS= LDFLAGS='-pipe -L/c/mingw491/i686-491-posix-dwarf-rt_v3-rev1/mingw32/opt/li
    b -L/c/mingw491/prerequisites/i686-zlib-static/lib -L/c/mingw491/prerequisites/i686-w64-mingw32-static/lib -Wl,--large-address-aware'
    Thread model: posix
    gcc version 4.9.1 (i686-posix-dwarf-rev1, Built by MinGW-W64 project)


#### Download and Install Dependencies

Create a deps folder at C:\deps.  If you want to cheat you can download the pre-built dependencies here http://www.mediafire.com/download/y89546s65sf8de5/deps.zip, though it is recommended to build your own.

2a. OpenSLL- Install OpenSSL dependencies on Windows.
Download the latest version of OpenSSL https://www.openssl.org/source/openssl-1.0.1j.tar.gz to your deps folder.

Open the MinGW shell at C:\MinGW\msys\1.0\msys.bat 

Code:

    cd /c/deps/
    tar xvfz openssl-1.0.1j.tar.gz
    cd openssl-1.0.1j
    ./Configure no-zlib no-shared no-dso no-krb5 no-camellia no-capieng no-cast no-cms no-dtls1 no-gost no-gmp no-heartbeats no-idea no-jpake no-md2 no-mdc2 no-rc5 no-rdrand no-rfc3779 no-rsax no-sctp no-seed no-sha0 no-static_engine no-whirlpool no-rc2 no-rc4 no-ssl2 no-ssl3 mingw
    make


2b. Berkeley DB
Download http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz and place in your deps folder.

In the MinGW shell use the following code.

Code:

    cd /c/deps/
    tar xvfz db-4.8.30.NC.tar.gz
    cd db-4.8.30.NC/build_unix
    ../dist/configure --enable-mingw --enable-cxx --disable-shared --disable-replication
    make


2c. Boost

Download Boost to your deps folder. http://sourceforge.net/projects/boost/files/boost/1.55.0/boost_1_55_0.zip/download 
Make sure to download either the 7z or zip versions. 

Double click on the folder to extract boost_1_55_0 in your deps folder. This may take several minutes depending on your PC's speed. 

Using the Windows command prompt, bootstrap and compile boost. 

To bring up the windows command prompt just type cmd in the windows search bar.

Code:

    cd C:\deps\boost_1_55_0\
    bootstrap.bat mingw
    b2 --build-type=complete --with-chrono --with-filesystem --with-program_options --with-system --with-thread toolset=gcc variant=release link=static threading=multi runtime-link=static stage


2d. Mini UPNP

Download and extract MiniUPNP http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.9.20140911.tar.gz to your deps folder. 

Rename  folder from "miniupnpc-1.9.20140911" to "miniupnpc" then from a Windows command prompt:

Code:

    cd C:\deps\miniupnpc
    mingw32-make -f Makefile.mingw init upnpc-static


2e. Protoc and Libprotobuf:

Download and extract http://protobuf.googlecode.com/files/protobuf-2.5.0.zip to your deps folder.

In the msys shell run

Code:

    cd /c/deps/protobuf-2.5.0
    configure --disable-shared
    make

2f. libpng

Download and extract http://prdownloads.sourceforge.net/libpng/libpng-1.6.14.tar.gz?download to your deps folder and extract.

In msys shell run 

Code:

    cd /c/deps/libpng-1.6.14
    configure --disable-shared
    make
    cp .libs/libpng16.a .libs/libpng.a

2g. qrencode

Download and extract http://fukuchi.org/works/qrencode/qrencode-3.4.4.tar.gz to your deps folder.

In msys shell run 

Code:

    cd /c/deps/qrencode-3.4.4

    LIBS="../libpng-1.6.14/.libs/libpng.a ../../mingw32/i686-w64-mingw32/lib/libz.a" \
    png_CFLAGS="-I../libpng-1.6.14" \
    png_LIBS="-L../libpng-1.6.14/.libs" \
    configure --enable-static --disable-shared --without-tools

    make

#### Download and Compile QT.

3a. Download and uncompress http://download.qt-project.org/official_releases/qt/4.8/4.8.6/qt-everywhere-opensource-src-4.8.6.zip to C:\Qt\4.8.6. 

Once again check it resides in C:\Qt\4.8.6 not C:\Qt\4.8.6\4.8.6. Due to a bug in 4.8.6 you will need to apply the patch available here. 

For those who can't find or work it out, you need to change the following lines in C:\Qt\4.8.6\tools\configure\configureapp.cpp or download the patched file here and replace it in C:\Qt\4.8.6\tools\configure\configureapp.cpp

Code:

    2180  |  -  const QString mingwPath = dictionary["QMAKESPEC"].endsWith("-g++") ?
    2180  |  +  const QString mingwPath = dictionary["QMAKESPEC"].contains("-g++") ?
    2252  |   -  if (dictionary["QMAKESPEC"].endsWith("-g++")+
    2252  |  +  if (dictionary["QMAKESPEC"].contains("-g++")+

From your Windows command prompt run 

Code:

    cd C:\Qt\4.8.6
    configure -release -opensource -confirm-license -static -no-sql-sqlite -no-qt3support -no-opengl -qt-zlib -no-gif -qt-libpng -qt-libmng -no-libtiff -qt-libjpeg -no-dsp -no-vcproj -no-openssl -no-dbus -no-phonon -no-phonon-backend -no-multimedia -no-audio-backend -no-webkit -no-script -no-scripttools -no-declarative -no-declarative-debug -qt-style-windows -qt-style-windowsxp -qt-style-windowsvista -no-style-plastique -no-style-cleanlooks -no-style-motif -no-style-cde -nomake demos -nomake examples
    mingw32-make

3b. Download and extract the Bitmxittz source. 

https://github.com/bitmxittz/Bitmxittz.

remeber by default some files will be locked by your computer since files come from another computer.
to unlock a file you have to goto properties of file by right clicking on a file and unblock manually which will take hours, to unlock all files at once just compress Bitmxittz folder and send to another local device send it back to first device and unzip (works on most operating systems).


#### Compiling Bitmxittz Windows QT.

Create libleveldb.a and libmemenv.a.

Using Msys shell, run.

Code:

    cd /C/Bitmxittz/src/leveldb
    TARGET_OS=NATIVE_WINDOWS make libleveldb.a libmemenv.a
    
If the file already exists, Msys will inform you so.


Now from a the Windows cmd, run  

Code:

    set PATH=%PATH%;C:\Qt\4.8.6\bin
    cd C:\Bitmxittz\
    qmake "USE_QRCODE=1" "USE_UPNP=1" "USE_IPV6=1" bitmxittz-qt.pro
    mingw32-make -f Makefile.Release

Your Bitmxittz qt should now be available in your C:\Bitmxittz\release folder after around 5 minutes depends on your computer speed.


#### Windows wallets, bitmxittz-qt v1.0.0.1 and v1.0.0.2 

windows wallet bitmxittz-Qt v1.0.0.1 https://mega.nz/#!RS4zFY7J!KXNQrPhWnxoF6F1BGyB74PS-3oGctsFq41OCfL-z4F4

windows wallet bitmxittz-Qt v1.0.0.2 https://mega.nz/#!JX5hxa4b!nSJ6RSQhonvhQjp5ckK2FP262I4-WVsPN1tkfcULokE


# License

https://bitmxittz.com/license/

https://bitmxittz.mit-license.org/
