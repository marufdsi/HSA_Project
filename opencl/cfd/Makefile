include ../../common/make.config
#C compiler
CC = nvcc

KERNEL_DIM =-DRD_WG_SIZE_1=128 -DRD_WG_SIZE_2=192 -DRD_WG_SIZE_3=128 -DRD_WG_SIZE_4=256
#OPENCL_DIR = /home/sc5nf/ati-stream-sdk-v2.2-lnx64/
#INC = $(OPENCL_DIR)/include/ 
#LIB = $(OPENCL_DIR)/lib/x86_64/

FLAGS = -O3 -std=c++11
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
