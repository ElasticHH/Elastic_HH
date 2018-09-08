GCC = g++
CFLAGS = -O2 -std=c++14
SSEFLAGS = -msse2 -mssse3 -msse4.1 -msse4.2 -mavx -march=native
FILES = elastic.out elastic_heavyhitter.out spacesaving.out countheap.out cmheap.out

all: $(FILES) 

elastic.out: elastic.cpp
	$(GCC) $(CFLAGS) $(SSEFLAGS) -o elastic.out elastic.cpp

elastic_heavyhitter.out: elastic_heavyhitter.cpp
	$(GCC) $(CFLAGS) $(SSEFLAGS) -o elastic_heavyhitter.out elastic_heavyhitter.cpp

spacesaving.out: spacesaving.cpp
	$(GCC) $(CFLAGS) $(SSEFLAGS) -o spacesaving.out spacesaving.cpp

countheap.out: countheap.cpp
	$(GCC) $(CFLAGS) $(SSEFLAGS) -o countheap.out countheap.cpp

cmheap.out: cmheap.cpp
	$(GCC) $(CFLAGS) $(SSEFLAGS) -o cmheap.out cmheap.cpp

clean:
	rm $(all) -f *~ *.o *.out
