# auto-detect subdirs
ifeq ($(CONFIG_ARCH_SDM845), y)
include $(srctree)/techpack/audio/config/sdm845auto.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdm845auto.conf)
endif
ifeq ($(CONFIG_ARCH_SDM670), y)
ifeq ($(CONFIG_SEC_GTS4LV_PROJECT), y)
include $(srctree)/techpack/audio/config/sdm710auto_gts4lv.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdm710auto_gts4lv.conf)
else
include $(srctree)/techpack/audio/config/sdm710auto_static.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdm710auto_static.conf)
endif
endif
ifeq ($(CONFIG_ARCH_SDXPOORWILLS), y)
include $(srctree)/techpack/audio/config/sdxpoorwillsauto.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdxpoorwillsauto.conf)
endif

# Use USERINCLUDE when you must reference the UAPI directories only.
USERINCLUDE     += \
                -I$(srctree)/techpack/audio/include/uapi \

# Use LINUXINCLUDE when you must reference the include/ directory.
# Needed to be compatible with the O= option
LINUXINCLUDE    += \
                -I$(srctree)/techpack/audio/include/uapi \
                -I$(srctree)/techpack/audio/include

ifeq ($(CONFIG_ARCH_SDM845), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdm845autoconf.h
endif
ifeq ($(CONFIG_ARCH_SDM670), y)
ifeq ($(CONFIG_SEC_GTS4LV_PROJECT), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdm710autoconf_gts4lv.h
else
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdm710autoconf.h
endif
endif
ifeq ($(CONFIG_ARCH_SDXPOORWILLS), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdxpoorwillsautoconf.h
endif

obj-y += soc/
obj-y += dsp/
obj-y += ipc/
obj-y += asoc/
