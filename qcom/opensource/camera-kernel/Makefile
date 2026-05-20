# Makefile for use with Android's kernel/build system

KBUILD_OPTIONS += CAMERA_KERNEL_ROOT=$(KERNEL_SRC)/$(M)
KBUILD_OPTIONS += KERNEL_ROOT=$(KERNEL_SRC)
KBUILD_OPTIONS += MODNAME=camera
KBUILD_OPTIONS += BOARD_PLATFORM=pineapple
KBUILD_OPTIONS += CONFIG_QCOM_SMCINVOKE=m
KBUILD_OPTIONS += TARGET_SYNX_ENABLE=m
KBUILD_OPTIONS += CONFIG_MSM_MMRM=y
KBUILD_OPTIONS += CONFIG_MSM_MMRM_VM=n
KBUILD_OPTIONS += CONFIG_QTI_SMMU_PROXY=m

KBUILD_EXTRA_SYMBOLS := \
    $(OUT_DIR)/../sm8650-modules/qcom/opensource/mmrm-driver/Module.symvers \
    $(OUT_DIR)/../sm8650-modules/qcom/opensource/securemsm-kernel/Module.symvers \
    $(OUT_DIR)/../sm8650-modules/qcom/opensource/synx-kernel/Module.symvers

all: modules

modules dtbs:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) M=$(M) -C $(KERNEL_SRC) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
