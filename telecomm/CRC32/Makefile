crc: crc_32.c Makefile
	#gcc -static crc_32.c -O3 -o crc 
	clang crc_32.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc crc_32.o -o crc -static -march=rv64gc -mabi=lp64 -L ../../ -lsoftboundcets_rt -lm
clean:
	rm -rf crc output* *.o
