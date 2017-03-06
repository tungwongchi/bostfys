#build gcc

platform: x86_64-Linux-GNU
prepare: svn, gcc, make

#step 1. get the source code 
    $ svn checkout svn://gcc.gnu.org/svn/gcc/trunk
  
#step 2. build it
    $ cd ./gcc/
    $ mkdir build-tmp
    $ cd build-tmp
    $ ../configure --enable-multiarch --enable-shared --enable-threads=posix --with-system-zlib --enable-mutilib
    $ make
    $ make install

# remake #001:
    error: 
        collect2: error: ld returned 1 exit status
        configure: error: I suspect your system does not have 32-bit development libraries (libc and headers). 
        If you have them, rerun configure with --enable-multilib. If you do not have them, and want to build 
        a 64-bit-only compiler, rerun configure with --disable-multilib.

    selution:
        #64-bit (`x86_64`) C library and headers
        $ yum install libgcc
        $ yum install glibc-devel
        
        # 32-bit (‘i386’) C library and headers
        $ yum install libgcc.i686
        $ yum install glibc-devel.i686
