# Status
It is usually easiest to build GCC with GCC.
Gcc is currently not working on Apple Silicon due to 
Apple's new ABI that is currently being resolved.

See below:
 - https://gcc.gnu.org/pipermail/gcc/2020-June/232924.html
 - https://gcc.gnu.org/bugzilla/show_bug.cgi?id=96168#c11
 - https://github.com/iains/gcc-darwin-arm64#readme
 
 Binutils 2.24 is know to build on with Apple Clang
 
# Dependencies

Need to update.

# Process

 - Download binutils [2.24](https://ftp.gnu.org/gnu/binutils/binutils-2.24.tar.bz2)
 - extract and do the following
 
 ```
export CC=clang
export CXX=clang++
export LDFLAGS=-L/usr/local/lib
export CPPFLAGS=-I/usr/local/include
CFLAGS=-Wno-error ./configure --target=ppc-elf64 --with-system-zlib --with-python=python3
make
sudo make install
 ```
