
IDIR=../fmt/include
CXX=x86_64-w64-mingw32-g++
CFLAGS=-I$(IDIR) -std=c++17 -D ADD_EXPORTS
OBJ=entry.o emulator.o delegate.o singleton.o format.o

BEClient_x64.dll: $(OBJ)
	$(CXX) -shared -o BEClient_x64.dll $(OBJ) -Wl,--out-implib,BEClient_x64.dll.a

%.o: %.cpp
	$(CXX) -c -o $@ $< $(CFLAGS)

format.o: ../fmt/src/format.cc
	$(CXX) -c -o $@ $< $(CFLAGS)

.PHONY: clean

clean:
	rm -f *.o *.dll *.dll.a
