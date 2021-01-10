all: libtest

libtest: main.o libgengi.dylib #libmylib.a is the dependency for the executable
	gcc -lm -o libtest main.o -L. -lgengi -I include 

main.o: main.c
	gcc -Wno-nullability-completeness -O -c main.c -I include 

print.o: print.c
	gcc -Wno-nullability-completeness -O -c  -fPIC print.c -I include 

sum.o: sum.c
	gcc -Wno-nullability-completeness -O -c -fPIC sum.c -I include 

libgengi.dylib: print.o sum.o #let's link library files into a dynamic library
	gcc -dynamiclib -fPIC -o libgengi.dylib print.o sum.o

libs: libgengi.dylib

clean:
	rm -f libtest *.o *.so *.dylib *.a *.gch #This way is cleaner than your clean