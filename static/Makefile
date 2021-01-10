all: libtest

libtest: main.o libgengi.a #libmylib.a is the dependency for the executable
	gcc -lm -o libtest main.o -L. -lgengi -I include 

main.o: main.c
	gcc -O -c main.c -I include -Wno-nullability-completeness

print.o: print.c
	gcc -O -c print.c -I include -Wno-nullability-completeness

sum.o: sum.c
	gcc -O -c sum.c -I include -Wno-nullability-completeness

libgengi.a: print.o sum.o #let's link library files into a static library
	ar rcs libgengi.a print.o sum.o

libs: libgengi.a

clean:
	rm -f libtest *.o *.a *.gch #This way is cleaner than your clean