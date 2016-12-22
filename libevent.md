#build libevent

platform: x86_64-Linux-GNU
prepare: git, gcc, make, cmake

#step 1. get the source code 
    $ git clone https://github.com/libevent/libevent.git
  
#step 2. build it
    $ cd ./libevent/
    $ mkdir build && cd build
    $ cmake ..
    $ make && make install
