ifeq ($(CONFIG_OF),y)

dtb-$(CONFIG_ARCH_MSM8916) += msm8952-sim.dtb \
	msm8952-rumi.dtb \
	msm8952-qrd-skum.dtb \
	msm8952-l9300.dtb \
	msm8952-qrd-skum-dvt2.dtb \
	msm8952-cdp.dtb \
	msm8952-ext-codec-cdp.dtb \
	msm8952-mtp.dtb \
	msm8952-polaris.dtb \
	apq8052-cdp.dtb \
	apq8052-mtp.dtb \
	msm8952-eve-mtp.dtb

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))
endif

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(DTB_LIST))

clean-files := *.dtb
