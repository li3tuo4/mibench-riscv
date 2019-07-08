FILE = bitcnt_1.c bitcnt_2.c bitcnt_3.c bitcnt_4.c bitcnts.c bitfiles.c bitstrng.c bstr_i.c
FILE_o = bitcnt_1.o bitcnt_2.o bitcnt_3.o bitcnt_4.o bitcnts.o bitfiles.o bitstrng.o bstr_i.o 

bitcnts: ${FILE} Makefile
	#gcc -static ${FILE} -O3 -o bitcnts
	# kenny mod for risc-v and softboundcets
	# remember to put the libsoftboundcets.a runtime library on the root folder
	clang ${FILE} -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc ${FILE_o} -o bitcnts -L ../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64

clean:
	rm -rf bitcnts output* *.o
