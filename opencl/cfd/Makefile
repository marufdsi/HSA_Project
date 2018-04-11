include ../../common/make.config
#C compiler
CC = nvcc

#OPENCL_DIR = /home/sc5nf/ati-stream-sdk-v2.2-lnx64/
#INC = $(OPENCL_DIR)/include/ 
#LIB = $(OPENCL_DIR)/lib/x86_64/

FLAGS = -O3
SRC = euler3d.cpp

EXE = euler3d

release:$(SRC)
	$(CC) $(KERNEL_DIM) $(SRC) -o $(EXE)  -lOpenCL $(FLAGS) 

errmsg:$(SRC)
	$(CC) $(KERNEL_DIM) $(SRC) -o $(EXE)  -lOpenCL -D ERRMSG $(FLAGS)

ptx:$(SRC)
	$(CC) $(KERNEL_DIM) $(SRC) -o $(EXE)  -lOpenCL -D PTX_MSG $(FLAGS)

res:$(SRC)
	$(CC) $(KERNEL_DIM) $(SRC) -o $(EXE)  -lOpenCL -D RES_MSG $(FLAGS)

clean: $(SRC)
	rm -f $(EXE) $(EXE).linkinfo result*
