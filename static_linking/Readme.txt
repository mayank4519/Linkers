g++ -c main.cpp --> generate main.o --> compiler creates obj files
g++ -c foo.cpp  -> generate  foo.o  --> compiler create obj files.
ar rcs libmayank.a foo.o            --> create library of foo.o 
g++ -o out main.o -L. -lmayank      --> linker create executable using obj files and libraries
./out   --> run executable

Problems:
1. Since library code is directly copied while creating exec, total size of exec. is more.
2. Every time there is a change in library, whole code needs to be recompiled and freshly generate the executable.
