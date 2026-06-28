# Switchroot LineageOS Downloader (Debian 13)

<p align="center" width="100%">
    <img width="450px" src="images/preview.png" alt="Switchroot LineageOS Downloader preview">
</p>

*Example screenshot of the application in action.*

**Switchroot LineageOS Downloader** is a lightweight Debian 13 application designed to simplify the process of downloading and organizing LineageOS builds for the Nintendo Switch (Switchroot). Whether you're a beginner or an advanced user, this tool automates the entire download and organization process.

---

## ⚙️ System Requirements

### Debian 13 Prerequisites

This application is **optimized for Debian 13** and requires the following packages:

```bash
# Install Python 3 and required system packages
sudo apt update
sudo apt install python3 python3-pip python3-tk
```

### Python Dependencies

Install the required Python packages using pip:

```bash
pip3 install requests
```

**Note:** All other dependencies (`tkinter`, `threading`, `os`, `hashlib`, `zipfile`, `logging`) are part of Python's standard library.

---

## Features

- **Easy-to-Use GUI**: A clean and intuitive interface for seamless navigation.
- **Dark Theme**: A modern dark theme for comfortable usage.
- **Automatic Folder Structure**: Creates the necessary folders (`switchroot`, `bootloader`, etc.) and generates the required `android.ini` file.
- **Multi-Threaded Downloads**: Downloads multiple files simultaneously for faster performance.
- **Checksum Verification**: Ensures file integrity by verifying SHA-256 checksums for downloaded files.
- **Resumable Downloads**: Supports resuming interrupted downloads, saving time and bandwidth.
- **Progress Tracking**: Real-time progress updates with a progress bar and detailed download statistics.
- **Error Handling**: Retries failed downloads automatically and logs errors for troubleshooting.
- **Customizable Download Directory**: Users can select a custom download folder.

---

## Installation & Setup (Debian 13)

### Step 1: Install System Dependencies

```bash
sudo apt update
sudo apt install -y python3 python3-pip python3-tk
```

### Step 2: Clone or Download the Repository

```bash
git clone https://github.com/rootedtesla/Linux-Switchroot-LineageOS-Downloader.git
cd Linux-Switchroot-LineageOS-Downloader
```

### Step 3: Install Python Requirements

```bash
pip3 install -r requirements.txt
```

Or manually install:

```bash
pip3 install requests
```

### Step 4: Run the Application

```bash
python3 LineageOSDownloader.py
```

---

## Usage Guide

1. **Run the Application**: Execute `python3 LineageOSDownloader.py` in your terminal.
2. **Select Variant**: Choose between the **Tablet** or **TV** variant of LineageOS.
3. **Check Latest Build**: Click the "🔄 Check Build" button to fetch the latest build information from LineageOS servers.
4. **Select Download Folder**: Click "📂 Select Folder" and choose a directory where files will be downloaded and organized.
5. **Optional - Download GApps**: Check "Download MindTheGapps" if you want to include Google apps (requires internet).
6. **Start Download**: Click the "⏬ Download" button to begin downloading.
7. **Monitor Progress**: Watch the progress bar and logs for real-time updates.
8. **Verify Files**: The application automatically verifies file integrity using SHA-256 checksums.

---

## Folder Structure

After downloading, files are organized into the following structure:

```
LineageOS-{version}-{date}-{variant}/
├── switchroot/
│   ├── install/
│   │   ├── boot.img
│   │   ├── recovery.img
│   │   └── nx-plat.dtimg
│   └── android/
│       ├── bl31.bin
│       ├── bl33.bin
│       ├── boot.scr
│       ├── icon_android_hue.bmp
│       └── bootlogo_android.bmp
├── bootloader/
│   └── ini/
│       └── android.ini
└── lineage-{version}-{date}-nightly-nx_tab-signed.zip
```

---

## Logs

All actions and errors are logged in `lineageos_downloader.log` (created in the script's directory) for easy troubleshooting.

To view logs:
```bash
tail -f lineageos_downloader.log
```

---

## Troubleshooting

### Python Not Found

```bash
# Make sure Python 3 is installed
python3 --version

# If not installed:
sudo apt install python3
```

### tkinter Module Missing

```bash
# Install tkinter for Python 3
sudo apt install python3-tk
```

### requests Module Missing

```bash
# Install requests package
pip3 install requests
```

### Permission Denied

Make the script executable:
```bash
chmod +x LineageOSDownloader.py
```

### Download Fails

1. Check your internet connection
2. Review the logs: `tail -f lineageos_downloader.log`
3. Try clicking "🔄 Retry Failed" button
4. Ensure you have sufficient disk space

---

## Frequently Asked Questions (FAQ)

### 1. **Is this application safe to use?**
   - Yes, the application is safe to use. It does not contain any malware or harmful code. The source code is available for review on GitHub.

### 2. **What platforms are supported?**
   - This application is optimized for **Debian 13 and Ubuntu-based Linux distributions** using Python 3.

### 3. **What if the download fails?**
   - The application automatically retries failed downloads up to 3 times. If the issue persists, check the logs and try again.

### 4. **Can I change the download folder?**
   - Yes, click the "📂 Select Folder" button to choose a custom download location.

### 5. **How do I verify the checksum of downloaded files?**
   - The application automatically verifies SHA-256 checksums. If verification fails, the file is automatically re-downloaded.

### 6. **How much disk space do I need?**
   - LineageOS builds are typically 2-4 GB. Ensure you have at least 10 GB free for downloads and organization.

### 7. **Can I pause and resume downloads?**
   - Yes! The application supports resumable downloads. If interrupted, simply run it again and click the same build.

---

## Dependencies Breakdown

| Package | Purpose | Installation |
|---------|---------|--------------|
| `python3` | Runtime | `sudo apt install python3` |
| `python3-tk` | GUI Framework (Tkinter) | `sudo apt install python3-tk` |
| `python3-pip` | Package Manager | `sudo apt install python3-pip` |
| `requests` | HTTP Requests | `pip3 install requests` |

All other dependencies are part of Python's standard library.

---

## Support

If you encounter any issues or have suggestions for improvement, please open an [issue](https://github.com/rootedtesla/Linux-Switchroot-LineageOS-Downloader/issues) on GitHub.

---

## License

This project is licensed under the **MIT License**. Please see the [LICENSE](LICENSE) file for details.

---

## Why Use This Tool?

- **Saves Time**: Automates the download and organization process, eliminating manual folder creation.
- **User-Friendly**: Designed with an intuitive interface for both beginners and advanced users.
- **Reliable**: Ensures file integrity with automatic checksum verification and retry logic.
- **Linux Native**: Built specifically for Debian 13 with no Windows dependencies.

---

## Credits

- Built with Python 3 and `tkinter`.
- Uses the official LineageOS download API.
- Special thanks to the **Switchroot team** for their work on LineageOS for the Nintendo Switch.

---

Enjoy using the **Switchroot LineageOS Downloader**! If you find this tool helpful, consider giving it a ⭐ on GitHub.
