INCLUDE = -I/usr/include/
LIBDIR= -L/usr/X11R6/lib

CXX = g++
CFLAGS = -Wall -g -lX11 -lGLEW -lglut -lGL -lGLU -lm -lstdc++ -ldl -lXi -lXmu

#SRCS =  BmpLoad.cpp MultiTexture.cpp  
SRCS =  CG.cpp BmpLoad.cpp world.cpp
OBJS = $(SRCS:.cpp=.o)
default: CG

%.o: %.cpp %.hpp 
	$(CXX) -o $@  -c $<  $(CFLAGS)

CG: $(OBJS)
	$(CXX) -o $@ $^ $(CFLAGS)  

ifneq (clean, $(MAKECMDGOALS))
-include deps.mk
endif

deps.mk: $(SRCS) 
	$(CXX) -MM $^ > $@

run: CG
	./CG
clean:
	rm -f *.o 
