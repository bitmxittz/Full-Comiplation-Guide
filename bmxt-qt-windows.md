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

a. download github source code

b. compile qt wallet



#### Pre Installers

1a. File Compressor/Extractor

Download and install Winrar or an alternate file compression tool. 

http://www.rarlab.com/download.htm


1b. Text Editor

Download and install a text editor such as Sublime Text.

http://www.sublimetext.com/


1c. Download and install MingW

http://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download

Double click to install, keep the checkbox for the GUI checked and make sure to install in C:\MinGW. Press continue. From the MinGW GUI interface, go to all packages -> MYSYS

Right click on the following installations and mark for installation.

msys-base-bin (may highlight other checkboxes which is fine)

msys-autoconf-bin

msys-automake-bin

msys-libtool-bin

Click on Installation -> Apply changes. MinGW will now download the remaining packages. Make sure to remove any previous installs of MinGW before starting. 

Once complete, navigate to C:\MinGW\bin and you should only have a mingw-get application. If you have msys-gcc and msys-w32api you need to delete MinGW and check the correct install packages are selected above.


Download and extract mingw32 to C:\mingw32

http://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/4.9.1/theads-posix/dwarf/i686-4.9.1-release-posix-dwarf-rt_v3-rev1.7z/download

You now need to change the path variables. Go to control panel->system and security->system. Click on advanced system properties->environmental variables. In the top box navigate to PATH and change to

code:

    C:\mingw32\bin;%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\
    
Checking your MingW install. To start the MingW app navigate to C:\MinGW\msys\1.0\msys.bat, create a desktop shortcut as you will use the msys command as well as the windows command prompts. Double click to start and enter the following to display the version and correct paths.

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




https://bitmxittz.com/license/

https://bitmxittz.mit-license.org/
