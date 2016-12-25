#build greenlet

platform: x86_64-Linux-GNU
prepare: python, git, python-devel

#step 1. get the source code 
    $ git clone https://github.com/python-greenlet/greenlet.git
  
#step 2. build it
    $ cd ./greenlet/
    $ python setup.py install
