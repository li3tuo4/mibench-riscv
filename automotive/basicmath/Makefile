FILE1 = basicmath_small.c   rad2deg.c  cubic.c   isqrt.c
FILE2 = basicmath_large.c   rad2deg.c  cubic.c   isqrt.c
FILE1_o = basicmath_small.o  rad2deg.o  cubic.o   isqrt.o
FILE2_o = basicmath_large.o   rad2deg.o  cubic.o   isqrt.o

all: basicmath_small basicmath_large

basicmath_small: ${FILE1} Makefile
	#gcc -static -O3 ${FILE1} -o basicmath_small -lm
	#kenny risc-v with softboundcets
	clang -fsoftboundcets ${FILE1} -c #-march=rv64gc -mabi=lp64
	riscv64-unknown-linux-gnu-gcc ${FILE1_o} -o basicmath_small -L ../../ -lsoftboundcets_rt -lm -lrt -march=rv64gc -mabi=lp64 -static
basicmath_large: ${FILE2} Makefile
	#gcc -static -O3 ${FILE2} -o basicmath_large -lm
	clang -fsoftboundcets ${FILE2} -c #-march=rv64gc -mabi=lp64
	riscv64-unknown-linux-gnu-gcc ${FILE2_o} -o basicmath_large -L ../../ -lsoftboundcets_rt -lm -lrt -march=rv64gc -mabi=lp64 -static
clean:
	rm -rf basicmath_small basicmath_large output* *.o
