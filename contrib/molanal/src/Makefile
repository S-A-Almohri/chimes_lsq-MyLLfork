## Uncomment the appropriate fortran 90 compiler.
#F90=pgf90
F90=gfortran
#F90=ifort

all : molanal.new gr_calc pad

molanal.new : molanal.new.c
	gcc -O3 -w -Wall -Wextra -DOPENMP -fopenmp molanal.new.c -lm -o molanal.new
#	gcc -g -Wall -Wextra molanal.new.c -lm -o molanal.new

gr_calc : gr_calc.f90
	$(F90) gr_calc.f90 -o gr_calc

pad : pad.c
	mpiicc -g -Wall pad.c -o pad

clean : 
	rm *.o

install : all
	-mkdir ~/bin
	cp molanal.new ~/bin
	cp gr_calc ~/bin
	cp pad ~/bin
	cp *.pl ~/bin


