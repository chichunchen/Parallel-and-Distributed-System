all: histogram histo_private histo_lockfree histo_lock1 histo_lock2

histogram: histogram.cpp ppmb_io.a
	gcc -O3 $^ -o $@ -lm -lrt

histo_private: histo_private.cpp ppmb_io.a
	gcc -std=c++11 -O3 $^ -o $@ -lm -lrt -pthread -lstdc++

histo_lockfree: histo_lockfree.cpp ppmb_io.a
	gcc -std=c++11 -O3 $^ -o $@ -lm -lrt -pthread -lstdc++

histo_lock1: histo_lock1.cpp ppmb_io.a
	gcc -std=c++11 -O3 $^ -o $@ -lm -lrt -pthread -lstdc++

histo_lock2: histo_lock2.cpp ppmb_io.a
	gcc -std=c++11 -O3 $^ -o $@ -lm -lrt -pthread -lstdc++

ppmb_io.a: ppmb_io.o 
	ar rs $@ $<

.phony: clean

clean:
	rm -f ppmb_io.a ppmb_io.o histogram histo_private histo_lock1 histo_lock2 histo_lockfree
