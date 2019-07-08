FILE1 = qsort_small.c
FILE2 = qsort_large.c

all: qsort_small qsort_large

qsort_small: qsort_small.c Makefile
	#riscv64-unknown-elf-gcc qsort_small.o -static -o qsort_small -lm -march=rv64imac -mabi=lp64
	#riscv64-unknown-elf-gcc qsort_small.c -static -o qsort_small -lm
	#gcc -static qsort_small.c -O3 -o qsort_small -lm
	# kenny mod for risc-v and softboundcets
	clang qsort_small.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc -o $@ qsort_small.o -L ../../ -lsoftboundcets_rt -lm -march=rv64gc -mabi=lp64 -static
qsort_large: qsort_large.c Makefile
	#gcc -static qsort_large.c -O3 -o qsort_large -lm
	clang qsort_large.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc -o $@ qsort_large.o -L ../../ -lsoftboundcets_rt -lm -march=rv64gc -mabi=lp64 -static

clean:
	rm -rf qsort_small qsort_large output* *.o
