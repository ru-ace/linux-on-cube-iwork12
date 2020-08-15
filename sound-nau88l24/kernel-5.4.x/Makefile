KVER ?= `uname -r`
MDIR ?= /lib/modules/$(KVER)
KDIR ?= $(MDIR)/build

default:
	$(MAKE) -C $(KDIR) M=$$PWD


install:
#	cp snd-intel-sst-acpi.ko $(MDIR)/kernel/sound/soc/intel/atom/sst
	cp snd-soc-nau8824.ko $(MDIR)/kernel/sound/soc/codecs
	cp snd-soc-sst-cht-bsw-nau8824.ko $(MDIR)/kernel/sound/soc/intel/boards
	depmod -a $(KVER)

ucm:
	rm -rf /usr/share/alsa/ucm/chtnau8824
	cp -R ./chtnau8824 /usr/share/alsa/ucm/


clean:
	rm -f *.o *.a *.mod.* *.mod *.xz .s* .n* .b* .c* modules.order Module.symvers
	rm -rf .tmp_versions
