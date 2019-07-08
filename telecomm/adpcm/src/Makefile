#
# Makefile for adpcm and test programs
# -------------------

#####################################################################
# Added by C. Lee.
#
# On Sun machines, gcc need to be informed whether the machines have
# integer multipliers by specifying this option: -mv8.
#
# Also, on Sun machines, in order to use the SPIXTOOLS and SHADE,
# uncomment this option: -static.
#
#CC = gcc
#kenny mod for risc-v softboundcets
CC = clang
LN = riscv64-unknown-linux-gnu-gcc
LNFLAG = -L ../../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64

ALLSRC=adpcm.c Makefile adpcm.h libst.h adpcm.c timing.c rawcaudio.c \
	rawdaudio.c suncaudio.c sgicaudio.c sgidaudio.c hello.adpcm.uu

all: adpcm.o rawcaudio rawdaudio timing
	cp rawcaudio rawdaudio timing ../bin/.

adpcm.o: adpcm.h
	clang adpcm.c -c -fsoftboundcets

timing.o: timing.c
	clang timing.c -c -fsoftboundcets

rawcaudio.o: rawcaudio.c
	clang rawcaudio.c -c -fsoftboundcets

rawdaudio.o: rawdaudio.c
	clang rawdaudio.c -c -fsoftboundcets

rawcaudio: rawcaudio.o adpcm.o
	#$(CC) $(CFLAGS) rawcaudio.o adpcm.o -o rawcaudio
	$(LN) rawcaudio.o adpcm.o -o rawcaudio $(LNFLAG)

rawdaudio: rawdaudio.o adpcm.o
	#$(CC) $(CFLAGS) rawdaudio.o adpcm.o -o rawdaudio
	$(LN) rawdaudio.o adpcm.o -o rawdaudio $(LNFLAG)

timing: timing.o adpcm.o
	#$(CC) $(CFLAGS) timing.o adpcm.o -o timing
	$(LN) $(CFLAGS) timing.o adpcm.o -o timing $(LNFLAG)


# Added by C. Lee
clean:
	rm -f *.o ; rm rawcaudio rawdaudio timing ; rm -f ../bin/* ../output*
