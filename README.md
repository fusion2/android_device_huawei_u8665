CyanogenMod device configuration for the Huawei Fusion 2.

How to Build
---------------

Initialise from CyanogenMod:

    repo init -u git://github.com/CyanogenMod/android.git -b cm-10.2

Press Ctrl and H then navigate to .repo, create a folder named local_manifest 
Then create a file named manifest.xml inside that folder
Now copy and paste this inside of the manifest.xml

    <?xml version="1.0" encoding="UTF-8"?>
    <manifest>
      <remove-project name="CyanogenMod/android_frameworks_av" />
      <remove-project name="CyanogenMod/android_frameworks_native" />
      <project path="frameworks/av" name="androidarmv6/android_frameworks_av" remote="github" revision="cm-10.2" />
      <project path="frameworks/native" name="androidarmv6/android_frameworks_native" remote="github" revision="cm-10.2" />
      <project path="hardware/qcom/display-legacy" name="androidarmv6/android_hardware_qcom_display-legacy" remote="github" revision="cm-10.2" />
      <project path="hardware/qcom/media_legacy" name="androidarmv6/android_hardware_qcom_media_legacy" remote="github" revision="cm-10.2" />
      <project path="device/huawei/u8665" name="fusion2/android_device_huawei_u8665" remote="github" revision="cm-10.2" />
      <project path="kernel/huawei/huawei-kernel-3.4" name="fusion2/huawei-kernel-3.4" remote="github" revision="master" />
      <project path="vendor/huawei" name="Fusion2/proprietary_vendor_huawei" remote="github" revision="cm-10.2" />
      <project path="device/huawei/msm7x27a-common" name="Dazzozo/android_device_huawei_msm7x27a-common" remote="github" revision="cm-10.2" />
    </manifest>

Sync and build:

    repo sync -j4
    . build/envsetup.sh
    brunch u8665
