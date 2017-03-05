#build gcc

platform: x86_64-Linux-GNU
prepare: svn, gcc, make

#step 1. get the source code 
    $ svn checkout svn://gcc.gnu.org/svn/gcc/trunk
  
#step 2. build it
    $ cd ./gcc/
    $ ./configure --enable-mutilib
    $ make -j4 all-gcc
    $ make install

# remake #001:
    error: 
        collect2: error: ld returned 1 exit status
        configure: error: I suspect your system does not have 32-bit development libraries (libc and headers). If you have them, rerun configure with --enable-multilib. If you do not have them, and want to build a 64-bit-only compiler, rerun configure with --disable-multilib.

    selution:
        #64-bit (`x86_64`) C library and headers
        $ yum install libgcc
        $ yum install glibc-devel
        
        # 32-bit (‘i386’) C library and headers
        $ yum install libgcc.i686
        $ yum install glibc-devel.i686

# remake #002:
    error: 
        /bin/ld: ../libiberty/pic/libiberty.a(argv.o): unrecognized relocation (0x2a) in section `.text'
        /bin/ld: final link failed: Bad value
        collect2: error: ld returned 1 exit status

    selution:
