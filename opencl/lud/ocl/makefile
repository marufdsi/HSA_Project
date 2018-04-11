include ../../../common/make.config

#INC = -I$(OPENCL_INC) -I../common
INC = -I../common
LIB = -L$(OPENCL_LIB)

#C compiler
CC = nvcc
CC_FLAGS = -g -O3

EXE = lud

$(EXE): lud.cpp
	$(CC) $(KERNEL_DIM) $(CC_FLAGS) -o $(EXE) lud.cpp ../common/common.c $(INC) -lOpenCL

clean:
	rm -f $(EXE)
