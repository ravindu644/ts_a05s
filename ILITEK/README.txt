Args for init the touchscreen:

ilitek.tpsensor=ILITEK_TMB_ILI7807S

Affecting file:

samsung/a05s/recovery/root/init.recovery.qcom.rc

module order:

insmod /vendor/lib/modules/qcom_va_minidump.ko
insmod /vendor/lib/modules/panel_event_notifier.ko
insmod /vendor/lib/modules/lct_tp.ko
insmod /vendor/lib/modules/cmd.ko
insmod /vendor/lib/modules/tp_info.ko
insmod /lib/modules/msm_drm.ko dsi_display0=qcom,mdss_dsi_v2_ili7807s_tm_fhd_90hz_video
insmod /vendor/lib/modules/ilitek.ko tpsensor=ILITEK_TMB_ILI7807S

Additional (useful in twrp device trees):

/vendor/lib/modules = closed-source (vendor_dlkm)
/lib/modules = oss (vendor_boot)

How to mount firmware:

# Mount firmware
mkdir /vendor/firmware_mnt
mount vfat /dev/block/bootdevice/by-name/apnhlos /vendor/firmware_mnt ro
export ANDROID_ROOT /system_root

