KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build
M ?= $(shell pwd)
KBUILD_OPTIONS := CONFIG_XPADNEO=m
EXTRA_CFLAGS += -DVERSION=\"0.11\"
include $(ROOT_DIR)/private/google-modules/soc/gs/Makefile.include
modules modules_install clean compile_commands.json:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) W=1 \
	$(KBUILD_OPTIONS) \
	INSTALL_MOD_DIR="kernel/drivers/hid" \
	EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
	KBUILD_EXTRA_SYMBOLS="$(EXTRA_SYMBOLS)" \
	$(@)
