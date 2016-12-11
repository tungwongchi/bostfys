#build binutils

platform: x86_64-Linux-GNU
prepare: git, gcc, make

#step 1. get the source code 
    $ git clone git://sourceware.org/git/binutils-gdb.git binutils
  
#step 2. build it
    $ cd ./binutils/
    $ ./configure 
    $ make && make install

# remake #001:
    error: 
        WARNING: 'makeinfo' is missing on your system.
         You should only need it if you modified a '.texi' file, or
         any other file indirectly affecting the aspect of the manual.
         You might want to install the Texinfo package:
         <http://www.gnu.org/software/texinfo/>
         The spurious makeinfo call might also be the consequence of
         using a buggy 'make' (AIX, DU, IRIX), in which case you might
         want to install GNU make:
         <http://www.gnu.org/software/make/>
    selution:
        $ yum install texinfo 
        $ make clean
        $ make && make install
   
