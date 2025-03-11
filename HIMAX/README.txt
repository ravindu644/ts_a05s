Args for init the touchscreen:

hx83112f.tpsensor=HIMAX_TXD_HX83112F

Affecting file:

samsung/a05s/recovery/root/init.recovery.qcom.rc


module order:

insmod /vendor/lib/modules/qcom_va_minidump.ko
insmod /vendor/lib/modules/panel_event_notifier.ko
insmod /vendor/lib/modules/lct_tp.ko
insmod /vendor/lib/modules/cmd.ko
insmod /vendor/lib/modules/tp_info.ko
insmod /vendor/lib/modules/pmic_glink.ko
insmod /vendor/lib/modules/ucsi_glink.ko
insmod /vendor/lib/modules/fsa4480-i2c.ko
insmod /vendor/lib/modules/mbhc_dlkm.ko
insmod /vendor/lib/modules/sd77428.ko
insmod /vendor/lib/modules/pd_dbg_info.ko
insmod /vendor/lib/modules/tcpc_class.ko
insmod /vendor/lib/modules/qcom-pmic-voter.ko
insmod /vendor/lib/modules/pd_policy_manager.ko
insmod /vendor/lib/modules/sm5602_fg.ko
insmod /vendor/lib/modules/nopmi-chg.ko
insmod /lib/modules/msm_drm.ko dsi_display0=qcom,mdss_dsi_hx83112f_txd_fhd_90hz_video
insmod /vendor/lib/modules/hx83112f.ko tpsensor=HIMAX_TXD_HX83112F

Additional (useful in twrp device trees):

/vendor/lib/modules = closed-source (vendor_dlkm)
/lib/modules = oss (vendor_boot)

How to mount firmware:

# Mount firmware
mkdir /vendor/firmware_mnt
mount vfat /dev/block/bootdevice/by-name/apnhlos /vendor/firmware_mnt ro
export ANDROID_ROOT /system_root
