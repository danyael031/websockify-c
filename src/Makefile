TARGETS=websockify-c
PREFIX ?= /data/data/com.termux/files/usr
CFLAGS += -fPIC

all: $(TARGETS)

websockify-c: websockify.o websocket.o
	$(CC) $(CFLAGS) $(LDFLAGS) $^ -lssl -lcrypto -o $@

websocket.o: websocket.c websocket.h
websockify.o: websockify.c websocket.h

install: websockify-c
	install websockify-c $(PREFIX)/bin/websockify-c

uninstall:
	rm -f $(PREFIX)/bin/websockify-c


clean:
	rm -f websockify-c *.o

.PHONY: clean install uninstall
