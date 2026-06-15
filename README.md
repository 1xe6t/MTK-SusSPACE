<div align="center">

# MTK SusSPACE
### Universal AnyKernel Layout with Deeply Integrated SuSFS

**Automated AnyKernel Patches | Native Stock Stability | Kernel 5.10+**

[![Release](https://img.shields.io/github/v/release/1xe6t/MTK-SusSPACE?label=Release&style=flat-square&logo=github&logoColor=white&color=2ea44f)](https://github.com/1xe6t/MTK-SusSPACE/releases)
[![ReSukiSU](https://img.shields.io/badge/ReSukiSU-Supported-5AA300?style=flat-square)](https://github.com/1xe6t/MTK-SusSPACE)
[![SUSFS](https://img.shields.io/badge/SuSFS-Deep%20Integrated-E67E22?style=flat-square)](https://github.com/1xe6t/MTK-SusSPACE)
[![Kernel](https://img.shields.io/badge/Kernel-5.10%20%2B-blue?style=flat-square&logo=linux)](https://github.com/1xe6t/MTK-SusSPACE)

---

</div>

## 🌐 The Non-Qualcomm Customization Dilemma

The Android custom development ecosystem is heavily biased toward Qualcomm Snapdragon devices because their kernel source drivers are publicly available and open-source (via CodeLinaro). 

However, for devices powered by **MediaTek (Dimensity), UNISOC, Samsung (Exynos), or Google (Tensor)**, proprietary and closed-source driver structures make compiling a fully functional or stable custom kernel next to impossible.

### 🚫 The Major Issues Faced by Rooted Users:
* **Aggressive Integrity Checks:** Modern banking, financial, corporate, and gaming applications employ strict root and hardware modification detection mechanisms.
* **Failure of Traditional Hiding:** Standard userspace root-hiding methods frequently fail unless reinforced with kernel-level intervention like **SuSFS**.
* **The GKI & Soft-Brick Risk:** Generic GKI kernels often refuse to flash on MediaTek platforms. Even if they do, users are left with severe bootloops, soft bricks, or a system riddled with major glitches and hardware bugs.

**MTK SusSPACE was created to bridge this exact gap safely and efficiently.**

---

## 🚀 Project Overview

This repository hosts a highly optimized, **Universal AnyKernel build specifically tailored for devices running Kernel 5.10 and above**. 

Instead of forcing users to switch to an unstable custom kernel that compromises factory features, this project delivers advanced kernel-level root hiding. It ensures that the **SuSFS architecture is deeply integrated into your device's native, stable factory kernel layout**. You retain 100% of your stock system integrity, performance, and stability while completely isolating root privileges from detection.

### 🌟 Key Features

* **Deep Kernel-Level SuSFS:** Operates directly at the kernel tier to seamlessly mask bootloader unlock flags, root status, and system-level modifications from high-security apps.
* **Flawless App Compatibility:** Resolves root-detection conflicts across banking apps, financial platforms, and secure environments, allowing them to run perfectly without triggers.
* **Native Stock Stability:** Preserves your phone's original kernel configurations, factory tuning, and hardware optimizations. Experience zero bugs, zero camera dead-zones, and zero battery drain.
* **Out-of-the-Box ReSukiSU Support:** Fully compatible and optimized to work seamlessly with the **ReSukiSU Root Manager** environment.
* **Zero Module Overhead:** No separate, detectable, or unstable Magisk/Zygisk modules are required to achieve deep root hiding.

---

## 📊 Chipset Ecosystem & Customization Reality

| Processor Family | Driver Status | Open Source? | Custom Development Viability |
| :--- | :--- | :--- | :--- |
| **Qualcomm (Snapdragon)** 🟢 | Public (CodeLinaro) | **Yes** | 🏆 Elite Support for ROMs & Kernels |
| **MediaTek (Dimensity)** 🟡 | Semi-Private | **No** | ⚠️ Hard to Modify / High Risk of Bricks |
| **UNISOC** 🟡 | Semi-Private | **No** | ❌ Extremely Poor Support & Integration |
| **Samsung (Exynos)** 🔴 | Private | **No** | ❌ Highly Restricted Vendor Chains |
| **Google (Tensor)** 🔴 | Private | **No** | ❌ Ecosystem Locked Hardware |

> **Note:** Our AnyKernel implementation acts as a stable, bug-free bridge specifically targeting the limitations of the 🟡 and 🔴 chipsets.

---

## ⚙️ Compatibility & Requirements

* **Supported Kernel Versions:** Android devices running Kernel `5.10` up to the latest generations.
* **Target Architectures:** Engineered specifically for MediaTek (MTK), UNISOC, and restricted GKI device environments.
* **Root Manager Optimization:** Pre-configured for seamless integration with **ReSukiSU**.

---

## 🛠️ Step-by-Step Installation Guide

Follow these steps carefully to patch and flash your kernel image properly.

### Prerequisites & Downloads
1. Download and install the latest **Magisk App**: [Download Magisk Here](https://github.com/topjohnwu/Magisk/releases)
2. Obtain your device's stock **Disk Image** (the partition file you use for standard rooting, e.g., `boot.img`, `init_boot.img`, or `vendor_boot.img`).
3. Download the compatible **AnyKernel** zip package from our [Releases Section](https://github.com/1xe6t/MTK-SusSPACE/releases).
4. Download and install the **Spoofed Version of the ReSukiSU Manager** provided directly within our [Releases Section](https://github.com/1xe6t/MTK-SusSPACE/releases).
5. Download and install the **Wild KSU Manager (with SuSFS/ReSukiSU patching backend)**: [Download Wild KSU Here](https://github.com/WildKernels/Wild_KSU/releases/download/v3.1.2/Wild_KSU_Spoofed-v3.1.2_33208-release.apk)

---

### Step 1: Patch your Stock Image with Magisk
1. Open the **Magisk App** on your phone.
2. Tap on the **Install** button near the top card.
3. Choose **"Select and Patch a File"** and navigate to your original stock Disk Image file.
4. Tap **"LET'S GO"** to begin processing. Magisk will output a file named `magisk_patched_xxxx.img` in your Downloads folder. Keep it handy on your phone storage.

<!-- Image Placeholder: Magisk Patching Process -->

---

### Step 2: Configure and Patch inside Wild KernelSU
1. Open the **Wild KernelSU Manager** app that you installed earlier.
2. Under the installation tab, tap on **"Not Installed / Click to Install"**.
3. You will be prompted with two main options: **LKM** and **GKI**. Select **GKI**.
4. Inside the GKI sub-menu, choose the option labeled **"Patch boot image with magisk boot"**.
5. Select our compatible **AnyKernel** zip file that you downloaded from our releases.
6. Next, select the **`magisk_patched_xxxx.img`** file that you generated via Magisk in **Step 1**.
7. Start the process. Once it shows a success message, it will output the final, dual-patched stealth image file.

> **🚨 CRITICAL STEP BEFORE FLASHING:** Ensure that you have already installed the **Spoofed ReSukiSU Manager App** on your phone before proceeding to the Fastboot flashing stage. This ensures that the app instantly detects root parameters and switches to 'Installed' status right after the initial reboot.

<!-- Image Placeholder: Wild KernelSU Custom Patching Workflow -->

---

### Step 3: Flash the Final Kernel via Fastboot
1. Power off your device and boot it into **Fastboot Mode** (usually by holding Volume Down + Power button).
2. Connect your smartphone to your PC using a reliable USB cable.
3. Open your terminal/command prompt on your PC and enter your standard device-specific root flashing command, followed by the path to the final patched image file generated by Wild KernelSU.

*Choose the command matching your device's specific structural layout:*

**Standard Boot Layout Devices:**
```bash
fastboot flash boot path/to/wild_kernelsu_patched_image.img

```

**Newer GKI Layout Devices (Using `init_boot`):**

```bash
fastboot flash init_boot path/to/wild_kernelsu_patched_image.img

```

**Newer Devices requiring `vendor_boot` structural integration:**

```bash
fastboot flash vendor_boot path/to/wild_kernelsu_patched_image.img

```

4. Once the terminal reports a successful write operation, execute the following command to restart your device:

```bash
fastboot reboot

```

---

### Step 4: Verification & SuSFS Status

1. Once your device boots up completely, open the pre-installed **ReSukiSU Manager**.
2. The status layout will immediately display as **"Installed"** without further setup.
3. At the top configuration header, you will see a **3-line icon (Hamburger Menu)**.You can modify yous SuSFS settings there. This represents your fully working, deeply embedded **SuSFS Manager**, confirming that kernel-level isolation is completely active and stealthy.

---

## ⚠️ Disclaimer

```text
Your warranty is now void. Always verify your device's kernel version before flashing. 
We are not responsible for bricked devices, dead SD cards, bootloops, or any damage 
caused by flashing an incompatible kernel version. Ensure you have a verified backup 
of your stock boot.img, vendor_boot.img, or init_boot.img before proceeding. 
Flash entirely at your own risk.

```

---

⭐ If this implementation helped you bypass integrity checks safely, please drop a Star on this repository! ⭐

**MTK SusSPACE — Bringing Elite Kernel Stealth with Zero Compromise.**
