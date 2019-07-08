# By default, the code is compiled for a "big endian" machine.
# To compile on a "little endian" machine set the LITTLE_ENDIAN flag.
# To make smaller object code, but run a little slower, don't use UNROLL_LOOPS.
# To use NIST's modified SHA of 7/11/94, define USE_MODIFIED_SHA

#CC = gcc #kenny
CC = clang
CFLAGS = -O3 -Wall -march=rv64imac -mabi=lp64

sha:	sha_driver.o sha.o
	#$(CC) $(CFLAGS) -o $@ sha_driver.o sha.o
	#strip $@
	#kenny mod for risc-v softboundcets
	clang sha_driver.c -c -fsoftboundcets -march=rv64gc -mabi=lp64
	clang sha.c -c -fsoftboundcets -march=rv64gc -mabi=lp64
	riscv64-unknown-linux-gnu-gcc -o $@ sha_driver.o sha.o -march=rv64gc -mabi=lp64 -static -L ../../ -lsoftboundcets_rt -lm

clean:
	rm -rf *.o sha output* *.o
