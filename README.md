# OTA Update Guide for KernelSU GKI (boot.img)

This guide outlines a safe and consistent process for performing OTA updates on devices using KernelSU with GKI (patched boot.img), while maintaining root access.

---

## 🧩 Step 1: Before Performing OTA

- [ ] **Restore the stock boot.img**  
  *(You may use KernelFlasher or similar tools to restore your original boot.img)*

- [ ] **Disable the "Auto Disable AVB 2.0" module and all other KernelSU modules**  
  *(This ensures AVB verification is re-enabled before OTA)*

- [ ] **Reboot once**  
  *(To apply the changes and properly re-enable AVB)*

---

## 🔄 Step 2: During the OTA Update

- [ ] **Download and install the system update** *(but do not reboot yet)*

- [ ] **Open the KernelSU app → Install KSU to the inactive slot**  
  *(This ensures KernelSU survives the A/B OTA update)*

- [ ] **Go back to the System Updater and press reboot**

---

## 📲 Step 3: After OTA is Complete

- [ ] **Verify that KernelSU is running in `<LKM>` mode**

- [ ] **Backup the following partitions:**
  - `init_boot.img`
  - `vbmeta.img`
  - `boot.img`

- [ ] **Enable the "Auto Disable AVB 2.0" module**  
  *(To skip AVB verification again)*

- [ ] **Reboot once**

---

## 📦 Step 4: Flashing the Kernel

- [ ] **Flash the patched kernel**  
  *(Use `AnyKernel3.zip` or a patched `boot.img` via KernelFlasher)*

- [ ] **Reboot once**

- [ ] **Verify that KernelSU is now running in `<GKI>` mode**

- [ ] **Re-enable all other KernelSU modules**

---

## ⚠️ Notes

- This process **does not require fastboot or flashing vbmeta.img manually**.
- The "Auto Disable AVB 2.0" module **dynamically disables AVB** during boot when active.
- If AVB needs to be re-enabled manually, use:
  ```bash
  fastboot flash vbmeta vbmeta.img
- If you want to disable AVB manually, use:
  ```bash
   fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
  
