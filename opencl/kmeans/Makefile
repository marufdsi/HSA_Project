include ../../common/make.config
# C compiler
CC = g++
OCL = nvcc
CC_FLAGS = -g -O3 -std=c++11

kmeans: cluster.o getopt.o read_input.o kmeans_clustering.o rmse.o
	$(OCL) $(KERNEL_DIM) $(CC_FLAGS)  kmeans.cpp cluster.o getopt.o read_input.o kmeans_clustering.o rmse.o -o kmeans -I../util -DTIMING -lOpenCL -lOpenCL

%.o: %.[ch]
	$(CC) $(CC_FLAGS) $< -c

cluster.o: cluster.c 
	$(CC) $(CC_FLAGS) cluster.c -c

getopt.o: getopt.c 
	$(CC) $(CC_FLAGS) getopt.c -c

kmeans.o: kmeans.c 
	$(CC) $(CC_FLAGS) read_input.c -c

rmse.o: rmse.c
	$(CC) $(CC_FLAGS) rmse.c -c

clean:
	rm -f *.o *~ kmeans *.linkinfo
