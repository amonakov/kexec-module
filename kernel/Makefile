KDIR ?= /lib/modules/`uname -r`/build
ARCH ?= arm

default: orig
	$(MAKE) -C $(KDIR) M=$$PWD

orig:
	mkdir $@
	ln -s $(KDIR)/arch/$(ARCH)/kernel/relocate_kernel.S
	ln -s $(KDIR)/arch/$(ARCH)/kernel/machine_kexec.c $@/
	ln -s $(KDIR)/kernel/kexec.c $@/
