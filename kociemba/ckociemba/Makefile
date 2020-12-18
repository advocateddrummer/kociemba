CKOCIEMBA_SRC = coordcube.c cubiecube.c facecube.c search.c prunetable_helpers.c
CKOCIEMBA_INCLUDE = include
CFLAGS = -std=c99 -O3
BINDIR = bin
BIN = kociemba
LIBDIR = lib
LIB = libkociemba.a

solve: solve.c $(CKOCIEMBA_SRC)
	mkdir -p $(BINDIR)
	gcc $(CFLAGS) $(CKOCIEMBA_SRC) -I$(CKOCIEMBA_INCLUDE) solve.c -o $(BINDIR)/$(BIN)

# TODO: I am not sure that this object file is needed for libkociemba. */
solve.o: solve.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) solve.c

coordcube.o: coordcube.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) coordcube.c

cubiecube.o: cubiecube.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) cubiecube.c

facecube.o: facecube.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) facecube.c

search.o: search.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) search.c

prunetable_helpers.o: prunetable_helpers.c
	gcc -c -O -I$(CKOCIEMBA_INCLUDE) prunetable_helpers.c

libkociemba.a: solve.o coordcube.o cubiecube.o facecube.o search.o prunetable_helpers.o
	mkdir -p $(LIBDIR)
	ar rcs $(LIBDIR)/$(LIB) solve.o coordcube.o cubiecube.o facecube.o search.o prunetable_helpers.o

libs: libkociemba.a
