g++ -fPIC -c main.cpp --> generate main.o --> compiler creates obj files
g++ -fPIC -c foo.cpp  -> generate  foo.o  --> compiler create obj files.
g++ -shared -o libmayank.a foo.o            --> create dynamic library of foo.o 
g++ -o out main.o -L. -lmayank      --> linker create executable using obj files and libraries
./out   --> run executable

ldd out --> It will tell all the required shared objects for "out" executable.
libmayank.so (0x00007fd00d21f000)


The -fPIC option is to tell the compiler to create Position Independent Code (create libraries using relative addresses rather than absolute addresses because these libraries can be loaded multiple times). The -shared option is to specify that an architecture-dependent shared library is being created.


Pros:
Exec stores the address of the lib functions stored in memory. Unlike static linking, it doesnt make a copy of the lib code.
