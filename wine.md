#build winehq (Wine Is Not an Emulator)

platform: x86_64-Linux-GNU
prepare: git, gcc, make

#step 1. get the source code 
    $ git clone git://source.winehq.org/git/wine.git
  
#step 2. build it
    $ cd ./wine/
    $ ./configure && make install

# remake #001:
    error: 
        Configuration fails with: Cannot build a 32-bit program, you need to install 32-bit development libraries.
    selution:
        $ ./configure --enable-win64 && make install

# remake #002:
    long time for wait :P
