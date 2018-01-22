CFLAGS ?= -O2 -Wall

all: redir.so

%.so: %.c
	$(CC) $(CFLAGS) -shared -fpic -o $@ $<
