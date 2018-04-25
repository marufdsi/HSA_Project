include ../../common/make.config
CXX = nvcc
DEBUGFLAGS = -g
OPTIMIZEFLAGS = -O3
# You will need to modify the following 2 lines
# by inserting the correct path to the OpenCL
# lib and inc directories.
CXXFLAGS = -c $(OPTIMIZEFLAGS) -std=c++11
LINKFLAGS = -L/apps/pkg/cuda-8.0/rhel7_u2-x86_64/gnu/lib64/

# link objects(binaries) together
a.out: main.o OpenCL.o
	$(CXX) main.o OpenCL.o -o pathfinder -lOpenCL -O3

# compile main function file into object (binary)
main.o: main.cpp OpenCL.cpp kernels.cl
	$(CXX) $(CXXFLAGS) main.cpp OpenCL.cpp -lOpenCL

clean:
	clear
	@rm -f pathfinder *.o *.out *~ *\#
