CC=gcc
XEN_SRC = ../../../xen-master

LDFLAGS  += -nostdlib -m elf_x86_64 -T x86_64.ld
CPPFLAGS += -I$(XEN_SRC)/xen/include/public -fno-stack-protector
CFLAGS   += -Werror -m64 
ASFLAGS  += -D__ASSEMBLY__ -m64 
OBJS     += bootstrap.x86_64.o 

.PHONY: all

all: clean testkernel

testkernel: $(OBJS) kernel.o
	$(LD) $(LDFLAGS) $^ -o testkernel

clean:
	rm -f *.o 
	rm -f testkernel
