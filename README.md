# AccessMover

**AccessMover** is a Windows-only Python application with a graphical user interface (GUI) that provides two powerful features in one tool:

1. **Permissions Manager (Access Control)**  
   - Recursively grants **Full Control** file permissions to the current user and **Everyone** (or the `S-1-1-0` SID).  
   - Options for taking ownership, enabling inheritance, including or excluding the root folder, and skipping **AppData**.  

2. **Data Copy Tool (Mover)**  
   - Copies user files (Photos, Documents, Music, Videos, QuickBooks, or complete User Profiles) to a safe destination.  
   - Options for minimum file size, canceling scans, progress display, logging, and skipping **AppData**.  

---

## ✨ Features

- **Permissions Manager**
  - Runs with Administrator rights (auto-elevates if needed).
  - Grants `Full Control` recursively with optional inclusion of the root folder.
  - Take ownership first (`takeown`) if required.
  - Enable inheritance on root.
  - Skip `AppData` folders if desired.
  - Uses either `Everyone` or the localized SID `S-1-1-0`.
  - Live command log output.

- **Data Copy Tool**
  - Copy specific file categories: Photos, Documents, Music, Videos, QuickBooks.
  - Copy entire `Users` profiles.
  - Independent **Skip AppData** option.
  - Minimum file size filter (default 50 KB).
  - Progress bar and cancel option.
  - Log written to both GUI and `logfile.txt`.

---

## 📦 Requirements

- **Operating System**: Windows 10 / 11 / Server with GUI  
- **Python**: Version 3.8+  
- **Built-in Windows utilities**:  
  - `icacls`  
  - `takeown`  

### Python Dependencies

This project uses only the **Python standard library**:
- `tkinter` (for GUI)
- `os`, `sys`, `subprocess`, `shutil`, `threading`, `ctypes`, etc.

No third-party packages are required.

---

## 🚀 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/AccessMover.git
   cd AccessMover
   ```

2. **Verify Python is installed**:
   ```bash
   python --version
   ```

3. **(Optional) Upgrade pip**:
   ```bash
   python -m pip install --upgrade pip
   ```

4. No additional packages are needed. You can run the tool directly.

---

## 🖥 Usage

### Running the GUI
```bash
python AccessMover.py
```

Please run as Administrator.

---

### Permissions Manager (Access Control)

1. Browse and select the target folder.  
2. Choose your options:
   - ✅ Take ownership first  
   - ✅ Enable inheritance on root  
   - ✅ Include the root folder itself  
   - ✅ Use Everyone SID  
   - ✅ Skip AppData  
3. Click **Grant Full Control Recursively**.  
4. Watch the live log for results.

---

### Data Copy Tool (Mover)

1. Choose an operation:
   - Copy Photos  
   - Copy Documents  
   - Copy Music  
   - Copy Videos  
   - Copy QuickBooks files  
   - Copy User Data (entire profiles under `\Users`)  
2. Select the source drive/folder and the destination folder.  
3. Adjust the **Minimum File Size** if needed.  
4. Check/uncheck **Skip AppData** as desired.  
5. Click to start; progress and logs are shown.  
6. Cancel anytime with the Cancel button.  

---

## ⚠️ Warnings

- **Permissions Manager**:
  - Granting `Everyone: Full Control` is insecure in most environments. Use only for recovery/migration.  
  - Modifications are permanent and in-place. There is no automatic undo.  

- **Data Copy Tool**:
  - Copying large drives may take hours.  
  - Some files may be skipped if locked or unreadable.  
  - AppData often contains caches, temp files, and system configs— skip it unless you need it.  

---


## 📜 License

Released under the MIT License. See [LICENSE](LICENSE) for details.

---
