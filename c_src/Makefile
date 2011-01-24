include ../include.mk

CC = g++

ERLHOME = /usr/local/lib/erlang/lib/erl_interface-3.7.1
OCCIHOME = /home/adie/instant_client

INCPATH = -I. -I$(ERLHOME)/include -I$(OCCIHOME)/rdbms/public
LIBPATH = -L$(ERLHOME)/lib -L$(OCCIHOME)/lib
LIBS = -locci -lclntsh -lnnz11 -lerl_interface -lei -lpthread
CFLAGS = -g

OBJS = eco_main.o eco_marshal.o eco_proc.o eco_rows.o eco_fields.o eco_elements.o eco_conv.o eco_error.o

TARGET = ../priv/oraserver
all: $(TARGET)
$(TARGET): $(OBJS)
	$(CC) $(OBJS) -o $@ $(CFLAGS) $(LIBPATH) $(LIBS)

.cpp.o:
	$(CC) -c $(CFLAGS) $(INCPATH) $<

#dependencies
eco_main.o:    eco_main.cpp eco_marshal.h eco_proc.h
eco_marshal.o: eco_marshal.cpp eco_marshal.h
eco_proc.o:    eco_proc.cpp eco_proc.h eco_conv.h eco_rows.h ec_protocol.h eco_error.h
eco_rows.o:    eco_rows.cpp eco_rows.h eco_fields.h ec_protocol.h eco_error.h
eco_fields.o:  eco_fields.cpp eco_fields.h eco_elements.h eco_conv.h ec_protocol.h eco_error.h
eco_elements.o:eco_elements.h eco_conv.h eco_error.h ec_protocol.h 
eco_conv.o:    eco_conv.cpp eco_conv.h eco_error.h ec_protocol.h 
eco_error.o:   eco_error.cpp eco_error.h
