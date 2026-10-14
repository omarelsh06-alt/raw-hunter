# Raw-Hunter 🕵️‍♂️🔍

**Raw-Hunter** is a Python-based low-level disk forensics and threat hunting tool. It bypasses the standard Windows file system API to directly access raw physical drives (`\\.\PhysicalDriveX`), specifically targeting Sector 0 (Master Boot Record). 

By extracting the raw hex dump and performing **Shannon Entropy** analysis, Raw-Hunter helps security analysts identify non-standard boot signatures and detect highly compressed or encrypted hidden payloads (such as Bootkits) residing in the deepest layers of the storage device.

## 🚀 Key Features

* **Direct Physical Access:** Interacts with the raw storage device directly, bypassing logical volume layers.
* **MBR Boot Code Extraction:** Dumps the first 64 bytes of the boot code, a common hiding spot for low-level malware.
* **Signature Verification:** Validates the standard `55 AA` boot signature.
* **Shannon Entropy Analysis:** Calculates the mathematical complexity of the sector (Scale: 0 - 8) to mathematically expose obfuscated, encrypted, or packed anomalies that evade standard antivirus scans.

## 🛠️ Prerequisites

* **OS:** Windows (Due to `\\.\PhysicalDrive` access mechanics)
* **Python:** Python 3.x
* **Permissions:** **Administrator Privileges are strictly required** to perform raw physical disk reads.

## ⚙️ Usage

1. Open your terminal (`CMD` or `PowerShell`) as **Administrator**.
2. Run the script:
   ```bash
   python raw-hunter.py
