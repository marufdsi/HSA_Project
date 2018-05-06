include ../../common/make.config

#C compiler
CC = nvcc

SRC = nearestNeighbor.cpp clutils.cpp utils.cpp

CC_FLAGS = -g -O3 -lOpenCL -std=c++11

EXE = nn

release:
	$(CC) $(CC_FLAGS) -lOpenCL   $(SRC) -o $(EXE) -I$(OPENCL_INC) -L$(OPENCL_LIB)
	
clean: 
	rm -f $(EXE) 
