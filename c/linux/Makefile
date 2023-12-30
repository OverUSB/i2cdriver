CFLAGS += -I common -Wall -Wpointer-sign # -Werror
LDFLAGS += -shared

all: build/i2ccl build/i2cdriver.so

install: all
	cp build/i2ccl /usr/local/bin

build/i2ccl: linux/i2c.c common/i2cdriver.c
	mkdir -p build/
	$(CC) -o $@ $(CPPFLAGS) $(CFLAGS) $^

build/i2cdriver.so: common/i2cdriver.c
	$(CC) $(LDFLAGS) -o $@ $(CPPFLAGS) $(CFLAGS) -fPIC $^