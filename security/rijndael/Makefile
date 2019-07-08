rijndael: aes.c aes.h aestab.h aesxam.c Makefile
	gcc -static -O3 -o rijndael aes.c aesxam.c
	# kenny mod for risc-v softboundcets
	#clang aes.c -c -fsoftboundcets
	#clang aesxam.c -c -fsoftboundcets
	#riscv64-unknown-linux-gnu-gcc -o rijndael aes.o aesxam.o -static -march=rv64gc -mabi=lp64 -L ../../ -lsoftboundcets_rt -lm

clean:
	rm -rf rijndael output* *.o
