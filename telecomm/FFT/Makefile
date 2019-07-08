OBJ = main.o fftmisc.o  fourierf.o
FILE = main.c fftmisc.c  fourierf.c
CFLAGS = -static -O3 -g

fft: ${OBJ} Makefile
	#gcc  ${CFLAGS} ${OBJ} -o fft -lm
	riscv64-unknown-linux-gnu-gcc  ${CFLAGS} ${OBJ} -o fft -L ../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64
fftmisc.o: fftmisc.c
	clang ${CFLAGS} -c fftmisc.c -fsoftboundcets
fourierf.o: fourierf.c
	clang ${CFLAGS} -c fourierf.c -fsoftboundcets
main.o: main.c
	clang ${CFLAGS} -c main.c -fsoftboundcets

clean:
	rm -rf *.o fft output*
