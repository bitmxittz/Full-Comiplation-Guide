## Compile And Run Bitmxittz Daemon Wallet On Windows

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

#### 3. Download Source and Compile Daemon

a. download bitmxittz github source

b. compile bitmxittz daemon for windows

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

-

#### 2. Download and Install Dependencies

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

-

#### 3. Download Source and Compile Windows Daemon.

3a. Download and extract the Bitmxittz source. 

https://github.com/bitmxittz/Bitmxittz.

remeber by default some files will be locked by your computer since files come from another computer.
to unlock a file you have to goto properties of file by right clicking on a file and unblock manually which will take hours, to unlock all files at once just compress Bitmxittz folder and send to another local device send it back to first device and unzip (works on most operating systems).


3b. Compile bitmxittzd.exe for windows

Navigate to  C:\Bitmxittz\src\makefile.mingw and open with your text editor.

Code:

    USE_UPNP:=-
    USE_IPV6:=1
    
    DEPSDIR?=/usr/local
    BOOST_SUFFIX?=-mgw46-mt-sd-1_52
    
    INCLUDEPATHS= \
     -I"$(CURDIR)" \
     -I"$(DEPSDIR)/include"

    LIBPATHS= \
     -L"$(CURDIR)/leveldb" \
     -L"$(DEPSDIR)/lib"
    
    LIBS= \
     -l leveldb \
     -l memenv \
     -l boost_system$(BOOST_SUFFIX) \
     -l boost_filesystem$(BOOST_SUFFIX) \
     -l boost_program_options$(BOOST_SUFFIX) \
     -l boost_thread$(BOOST_SUFFIX) \
     -l boost_chrono$(BOOST_SUFFIX) \
     -l db_cxx \
     -l ssl \
     -l crypto
    
    DEFS=-D_MT -DWIN32 -D_WINDOWS -DBOOST_THREAD_USE_LIB -DBOOST_SPIRIT_THREADSAFE
    DEBUGFLAGS=-g
    CFLAGS=-mthreads -O2 -w -Wall -Wextra -Wformat -Wformat-security -Wno-unused-parameter $(DEBUGFLAGS) $(DEFS) $(INCLUDEPATHS)
    # enable: ASLR, DEP and large address aware
    LDFLAGS=-Wl,--dynamicbase -Wl,--nxcompat -Wl,--large-address-aware

change to

Code:

    USE_UPNP:=1
    USE_IPV6:=1
    
    DEPSDIR?=/usr/local
    BOOST_SUFFIX?=-mgw49-mt-s-1_55
    
    INCLUDEPATHS= \
     -I"$(CURDIR)" \
     -I"/c/deps/boost_1_55_0" \
     -I"/c/deps" \
     -I"/c/deps/db-4.8.30.NC/build_unix" \
     -I"/c/deps/openssl-1.0.1j/include"
     
    LIBPATHS= \
     -L"$(CURDIR)/leveldb" \
     -L"/c/deps/boost_1_55_0/stage/lib" \
     -L"/c/deps/miniupnpc" \
     -L"/c/deps/db-4.8.30.NC/build_unix" \
     -L"/c/deps/openssl-1.0.1j"
    
    LIBS= \
     -l leveldb \
     -l memenv \
     -l boost_system$(BOOST_SUFFIX) \
     -l boost_filesystem$(BOOST_SUFFIX) \
     -l boost_program_options$(BOOST_SUFFIX) \
     -l boost_thread$(BOOST_SUFFIX) \
     -l boost_chrono$(BOOST_SUFFIX) \
     -l db_cxx \
     -l ssl \
     -l crypto
    
    DEFS=-D_MT -DWIN32 -D_WINDOWS -DBOOST_THREAD_USE_LIB -DBOOST_SPIRIT_THREADSAFE
    DEBUGFLAGS=-g
    CFLAGS=-mthreads -O2 -w -Wall -Wextra -Wformat -Wformat-security -Wno-unused-parameter $(DEBUGFLAGS) $(DEFS) $(INCLUDEPATHS)
    # enable: ASLR, DEP and large address aware
    LDFLAGS=-Wl,--dynamicbase -Wl,--nxcompat -Wl,--large-address-aware -static

We change the deps to point to the deps we created earlier. If you chose to place your deps in a different folder, change the code to point to your folders. We also  -static to LDFLAGS=-Wl,--dynamicbase -Wl,--nxcompat -Wl,--large-address-aware -static for static linked exe,  updated UPNP Includes and Lib paths to enable UPNP.

In the Msys shell, you can now compile bitmxittzd.

Code:

    cd /c/Bitmxittz/src

    make -f makefile.mingw

    strip bitmxittzd.exe


## License

https://bitmxittz.com/license/

https://bitmxittz.mit-license.org/
