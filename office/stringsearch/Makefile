FILE1 = bmhasrch.c  bmhisrch.c  bmhsrch.c  pbmsrch_small.c 
FILE2 = bmhasrch.c  bmhisrch.c  bmhsrch.c  pbmsrch_large.c
FILE1_o = bmhasrch.o  bmhisrch.o  bmhsrch.o  pbmsrch_small.o 
FILE2_o = bmhasrch.o  bmhisrch.o  bmhsrch.o  pbmsrch_large.o 

all: search_small search_large

search_small: ${FILE1} Makefile
	#gcc -static ${FILE1} -O3 -o search_small
	#kenny mod for risc-v softboundcets
	clang ${FILE1} -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc -static ${FILE1_o} -o search_small -march=rv64gc -mabi=lp64 -L ../../ -lsoftboundcets_rt -lm
search_large: ${FILE2} Makefile
	#gcc -static ${FILE2} -O3 -o search_large
	clang ${FILE2} -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc -static ${FILE2_o} -o search_large -march=rv64gc -mabi=lp64 -L ../../ -lsoftboundcets_rt -lm
clean:
	rm -rf search_small search_large output* *.o
