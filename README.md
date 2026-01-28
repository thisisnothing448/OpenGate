# Project OpenGate 🔓

**Advanced UEFI/BIOS Modification Framework**

**Project OpenGate** is a specialized firmware modification initiative dedicated to unlocking the hidden potential of consumer-grade motherboards. By bypassing vendor-imposed restrictions, this project provides enthusiasts with professional-grade tuning options and a fully customized pre-boot environment.

---

## ⛔ CRITICAL WARNING: BitLocker & TPM

**PLEASE READ BEFORE PROCEEDING**

If your system drive is encrypted with **BitLocker**, flashing a modified BIOS **WILL** trigger a recovery lockout.

* **Requirement:** You must **SUSPEND** BitLocker protection in Windows (Control Panel > BitLocker Drive Encryption > Suspend Protection) before flashing.
* **TPM Notice:** If you plan to clear TPM or change Secure Boot settings, ensure you have your **48-digit BitLocker Recovery Key** backed up externally.
* **Recommendation:** Temporarily disable the TPM module in your current BIOS settings before starting the modification process.

---

## ✨ Key Modifications

### 1. Unified Menu Unlocking

* **Hidden Menus:** Access to restricted sub-menus including **AMD CBS**, **AMD PBS**, and advanced **DRAM Timing Control**.
* **Power User Rights:** Elevated `Access Rights` for hidden settings, enabling granular control over system stability.

### 2. Visual & Interface Customization

* **Signature Splash Screen:** Custom **Project OpenGate** high-resolution boot logo.
* **String Injection:** Rebranding of system strings (e.g., "American Megatrends") and customized POST-messages.
* **GUI Optimization:** Cleanup of redundant UI elements for a faster BIOS experience.

---

## 🛠 Installation Guides (Bypassing Signature Checks)

Official flashing tools usually block modified files. Use these "Zero-Check" methods:

### 1. ASUS (The AI Suite 3 / EZ Update Trick)

* **Requirements:** ASUS AI Suite 3 with **EZ Update** module.

1. Place `ORIGINAL.CAP` (official) and `MOD.CAP` (OpenGate) in the same folder.
2. In **EZ Update**, select `ORIGINAL.CAP`.
3. Wait for the "Ready to update" message. **DO NOT** click update yet.
4. In your file explorer, delete `ORIGINAL.CAP` and rename `MOD.CAP` to `ORIGINAL.CAP`.
5. Return to AI Suite and click **Flash/Update**.

### 2. GIGABYTE (Efiflash Bypass)

* **Requirements:** Bootable FreeDOS USB + Modified Efiflash.exe.

1. Boot into FreeDOS.
2. Run command: `efiflash OPENGATE.ROM /X`
3. The `/X` flag forces the flash by ignoring checksum mismatches.

### 3. MSI (Flash BIOS Button / M-Flash Swap)

* **Method A (Safest):** If your board has a "Flash BIOS Button" on the rear I/O, simply rename the modded file to `MSI.ROM`, plug it into the specific USB port, and hold the button. This bypasses all software checks.
* **Method B (M-Flash):** Hot-swapping the file on the USB drive during the final confirmation prompt (high risk, use only if Method A is unavailable).

### 4. Universal (AMI Firmware Update)

* **Command:** `afuwinx64.exe MOD.ROM /P /B /N /K /GAN`
* *Note:* The `/GAN` flag is an exploit for older AFU versions to ignore security signatures.

---

## ⚠️ General Disclaimer

> **DANGER:** Firmware modification carries a high risk of permanent hardware damage. Project OpenGate is provided "as is". Use at your own risk.

**Pre-Flash Checklist:**

1. **Full Dump:** Create a hardware-level backup of your original BIOS chip.
2. **Recovery Tooling:** Ensure your board supports **CrashFree** or **Flashback**.
3. **Hardware Backup:** Always have a **CH341A Programmer** ready.

---

## 📂 Project Structure

* `/ASUS` — ASUS OpenGate builds.
* `/MSI` — MSI OpenGate builds.
* `/Gigabyte` — Gigabyte OpenGate builds.

**Project OpenGate | Open the Gates to Your Hardware.**
