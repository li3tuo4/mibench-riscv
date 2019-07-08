all:  dijkstra_large dijkstra_small

dijkstra_large: dijkstra_large.c Makefile
	#gcc -static dijkstra_large.c -O3 -o dijkstra_large
	# kenny mod for risc-v softboundcets
	# the source code need some revise for less warning
	clang dijkstra_large.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc dijkstra_large.o -o dijkstra_large -L ../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64

dijkstra_small: dijkstra_small.c Makefile
	#gcc -static dijkstra_small.c -O3 -o dijkstra_small 
	clang dijkstra_small.c -c -fsoftboundcets
	riscv64-unknown-linux-gnu-gcc dijkstra_small.o -o dijkstra_small -L ../../ -lsoftboundcets_rt -lm -static -march=rv64gc -mabi=lp64
clean:
	rm -rf dijkstra_large dijkstra_small output* *.o
