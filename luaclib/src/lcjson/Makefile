.PHONY : build rebuild clean

default :
	@echo "======================================="
	@echo "Please use 'make build' command to build it.."
	@echo "Please use 'make rebuild' command to build it.."
	@echo "Please use 'make clean' command to clean all."
	@echo "======================================="

# CFLAGS = -O3 -Wall -DNDEBUG -fPIC -DJEMALLOC -ljemalloc
# CFLAGS = -O3 -Wall -DNDEBUG -fPIC -DTCMALLOC -ltcmalloc
CFLAGS = -O3 -Wall -DNDEBUG -fPIC
CC = cc

INCLUDE = -I/usr/local/include
LIB = -L/usr/local/lib

fpconv.o: fpconv.c fpconv.h
strbuf.o: strbuf.c strbuf.h

OBJS = fpconv.o strbuf.o

build: $(OBJS)
	$(CC) -o cjson.so lua_cjson.c $(OBJS) $(INCLUDE) $(LIB) $(CFLAGS) -shared -fPIC -lcore
	mv cjson.so ../../

rebuild: $(OBJS)
	$(CC) -o cjson.so lua_cjson.c $(OBJS) $(INCLUDE) $(LIB) $(CFLAGS) -shared -fPIC -lcore
	rm -rf *.o
	mv cjson.so ../../

clean:
	rm -rf *.o *.so
