susan: susan.c Makefile
	#gcc -static -O4 -o susan susan.c -lm
	#kenny modified for risc-v with softboundcets
	clang susan.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc susan.o -o susan -L ../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64
clean:
	rm -rf susan output* *.o
