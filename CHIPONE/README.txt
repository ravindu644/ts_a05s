Args for init the touchscreen:

icnl9922c.tpsensor=CHIPONE_INX_ICNL9922C

Affecting file:

samsung/a05s/recovery/root/init.recovery.qcom.rc

module order:

insmod /vendor/lib/modules/qcom_va_minidump.ko
insmod /vendor/lib/modules/panel_event_notifier.ko
insmod /vendor/lib/modules/lct_tp.ko
insmod /vendor/lib/modules/cmd.ko
insmod /vendor/lib/modules/tp_info.ko
insmod /lib/modules/msm_drm.ko dsi_display0=qcom,mdss_dsi_icnl9922cac_inx_fhd_90hz_video
insmod /vendor/lib/modules/icnl9922c.ko tpsensor=CHIPONE_INX_ICNL9922C

Additional (useful in twrp device trees):

/vendor/lib/modules = closed-source (vendor_dlkm)
/lib/modules = oss (vendor_boot)

How to mount firmware:

# Mount firmware
mkdir /vendor/firmware_mnt
mount vfat /dev/block/bootdevice/by-name/apnhlos /vendor/firmware_mnt ro
export ANDROID_ROOT /system_root
