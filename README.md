## KernelSU GKI Installation & OTA Update Guide for OnePlus 12 (English Version)

### Initial Installation:

1. Backup your `boot.img` using KernelFlasher app (or via Terminal command).
2. Disable all KernelSU modules from the KernelSU app.
3. Install or enable the `Auto Disable AVB 2.0.zip` module from the KernelSU modules page.
4. Reboot once to let the module take effect and disable AVB.
5. Flash `OP12_android14_6.1_Next_SUSFS_AnyKernel3.zip` via KernelFlasher app.
6. Reboot the device.

### Before Performing OTA Update:

1. Disable the `Auto Disable AVB 2.0` module from the KernelSU app.
2. Restore the stock `boot.img` you previously backed up using KernelFlasher (or Terminal).
3. Reboot the device.
4. Apply the `Full OTA.zip` update (but DO NOT reboot yet).
5. Open KernelSU and install to the inactive slot (OTA).
6. Go back to the system updater, tap install, and reboot.
7. Proceed with "Initial Installation" to restore KernelSU GKI.
