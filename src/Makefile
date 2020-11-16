TARGETS=websockify
PREFIX ?= /data/data/com.termux/files/usr
CFLAGS += -fPIC

all: $(TARGETS)

websockify: websockify.o websocket.o
	$(CC) $(LDFLAGS) $^ -lssl -lcrypto -o $@

websocket.o: websocket.c websocket.h
websockify.o: websockify.c websocket.h

install: websockify
	install websockify $(PREFIX)/bin/websockify

uninstall:
	rm -f $(PREFIX)/bin/websockify


clean:
	rm -f websockify *.o

.PHONY: clean install uninstall
