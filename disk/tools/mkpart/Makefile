#
# Makefile for mkpart utility
#

BUILD = ../../../build

CC = gcc
CFLAGS = -Wall -g
LDFLAGS = -g
LDLIBS = -lm

SRCS = mkpart.c
OBJS = $(patsubst %.c,%.o,$(SRCS))
BIN = mkpart

.PHONY:		all install clean

all:		$(BIN)

install:	$(BIN)
		mkdir -p $(BUILD)/bin
		cp $(BIN) $(BUILD)/bin

$(BIN):		$(OBJS)
		$(CC) $(LDFLAGS) -o $(BIN) $(OBJS) $(LDLIBS)

%.o:		%.c
		$(CC) $(CFLAGS) -o $@ -c $<

depend.mak:
		$(CC) -MM -MG $(CFLAGS) $(SRCS) > depend.mak

-include depend.mak

clean:
		rm -f *~ $(OBJS) $(BIN) depend.mak
