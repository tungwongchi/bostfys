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
        configure: error: X 32-bit development files not found. Wine will be built
        without X support, which probably isn't what you want. You will need
        to install 32-bit development packages of Xlib/Xfree86 at the very least.
        Use the --without-x option if you really want this.

    selution:
        $ yum install libx11-devel.i686

# remake #002:
    error: 
        configure: error: FreeType 32-bit development files not found. Fonts will not be built.
        Use the --without-freetype option if you really want this.
    
    selution:
        $  yum install freetype-devel.i686
