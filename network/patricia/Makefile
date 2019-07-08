patricia: patricia.c patricia_test.c Makefile
	#gcc -static patricia.c patricia_test.c -O3 -o patricia
	#kenny mod for risc-v softboundcets
	clang patricia.c patricia_test.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc patricia.o patricia_test.o -o patricia -march=rv64gc -mabi=lp64 -static -L ../../ -lsoftboundcets_rt -lm
clean:
	rm -rf patricia output* *.o
