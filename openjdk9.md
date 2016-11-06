#openjdk9

platform: x86_64-Linux-GNU
prepare: hg, gcc, make

#step 1. get the source code 
    $ hg clone hg.openjdk.java.net/jdk9/jdk9/
    $ cd ./jdk9/
    $ ./get_source.sh

# remake #001:
    error: 
        ERROR: Need initial repository to use this script
    selution:
        $ mkdir .hg
        $ touch .hg/hgrc
        $ vi .hg/hgrc
        input text like:
        [paths]
        default=http://hg.openjdk.java.net/jdk9/jdk9
        $ ./get_source.sh

# remake #002:
    error:
        jdk:   abort: stream ended unexpectedly (got 12 bytes, expected 12967)
        WARNING: jdk exited abnormally (255)
    selution:
        try again
        $ ./get_source.sh
