#
# KallistiGL test program
# (c)2013-2014 Josh PH3NOM Pearson
# (c)2001 Megan Potter
#   

TARGET = gltest.elf
OBJS = gltest.o pvr-texture.o romdisk.o
KOS_ROMDISK_DIR = romdisk

all: rm-elf $(TARGET)

include $(KOS_BASE)/Makefile.rules

clean: rm-elf
	-rm -f $(OBJS)

rm-elf:
	-rm -f $(TARGET) romdisk.*

$(TARGET): $(OBJS)
	kos-cc -o $(TARGET) $(OBJS) -lGL -lpcx -lkosutils

run: $(TARGET)
	$(KOS_LOADER) $(TARGET)

dist: $(TARGET)
	-rm -f $(OBJS) romdisk.img
	$(KOS_STRIP) $(TARGET)

