SERIAL=/dev/ttyUSB0


TOOLCHAIN_PREFIX=arm-none-eabi
CC=$(TOOLCHAIN_PREFIX)-gcc
OBJCOPY=$(TOOLCHAIN_PREFIX)-objcopy

LIBOPENCM3_PATH=../../libopencm3

ARCH_FLAGS=-mthumb -mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16

CFLAGS=-Os -Wextra -Wshadow -Wimplicit-function-declaration -Wredundant-decls -Wmissing-prototypes -Wstrict-prototypes -fno-common -ffunction-sections -fdata-sections -MD -Wall -Wundef -DSTM32L4

INCLUDES=-I$(LIBOPENCM3_PATH)/include

LDFLAGS=-L$(LIBOPENCM3_PATH)/lib

LDLIBS=-lopencm3_stm32l4


.PHONY: clean upload

all: main.hex

main.o: main.c
	$(CC) $(CFLAGS) $(ARCH_FLAGS) $(INCLUDES) -o $@ -c $<

main.elf: main.o stm32l476rg.ld cortex-m-generic.ld
	$(CC) --static -nostartfiles $(LDFLAGS) -Tstm32l476rg.ld -Wl,-Map=$(@:.elf=.map) -Wl,--gc-sections $(ARCH_FLAGS) $< $(LDLIBS) -Wl,--start-group -lc -lgcc -lnosys -Wl,--end-group -o $@

main.hex: main.elf
	$(OBJCOPY) -O ihex $< $@

clean:
	rm -f *.o *.elf *.hex *.d *.map

upload: main.hex
	st-flash --reset --format=ihex write $< 
