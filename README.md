# Windows Package Manager Source for StorCat

<div align="center">
  <img src="https://raw.githubusercontent.com/scottkw/storcat/main/build/icons/storcat-logo.png" alt="StorCat Logo" width="128" height="128">
  
  **Custom winget source for StorCat - Directory Catalog Manager**
  
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
</div>

## 📦 Installation

### Add the source and install StorCat:
```powershell
# Add the custom winget source
winget source add storcat https://github.com/scottkw/winget-storcat

# Install StorCat
winget install scottkw.StorCat

# Or install directly with source name
winget install --source storcat scottkw.StorCat
```

### Or use the direct installer URL (one-time):
```powershell
winget install --manifest https://raw.githubusercontent.com/scottkw/winget-storcat/main/manifests/s/scottkw/StorCat/1.1.1/scottkw.StorCat.yaml
```

## 🚀 Quick Start

After installation, StorCat will be available:
- **In Start Menu** - Search for "StorCat"
- **Via Command Line** - Type `storcat` in any terminal
- **Desktop Shortcut** - If created during installation

## 📋 What is StorCat?

StorCat is a modern Electron-based directory catalog management application that provides a clean, intuitive GUI interface for creating, searching, and browsing directory catalogs.

### Key Features:
- **📁 Create Catalogs**: Generate comprehensive JSON and HTML catalogs of any directory
- **🔍 Search Catalogs**: Fast, full-text search across multiple catalog files  
- **📂 Browse Catalogs**: Interactive catalog browser with modern table interface
- **🌙 Dark/Light Mode**: Complete theme support with automatic HTML catalog adaptation
- **📊 Professional Tables**: Modern components with filtering, sorting, and pagination
- **⚡ Cross-Platform**: Works on Windows, macOS, and Linux

## 🔄 Updates

### Update StorCat:
```powershell
winget upgrade scottkw.StorCat
```

### Update all packages:
```powershell
winget upgrade --all
```

## 🗑️ Uninstallation

### Remove StorCat:
```powershell
winget uninstall scottkw.StorCat
```

### Remove the source:
```powershell
winget source remove storcat
```

## 🔧 Troubleshooting

### Common Issues

#### "Package not found" Error
```powershell
# Refresh winget sources
winget source update

# Try installing again
winget install scottkw.StorCat
```

#### "The installer hash does not match" Error
This usually means the source cache is outdated:
```powershell
# Reset winget cache
winget source reset

# Add source again
winget source add storcat https://github.com/scottkw/winget-storcat
```

#### Windows Defender SmartScreen Warning
This is normal for unsigned applications:
1. **Click "More info"** when the warning appears
2. **Click "Run anyway"** to proceed
3. **Windows will remember** your choice for future launches

#### Permission Issues
```powershell
# Run PowerShell as Administrator
# Then try installation again
winget install scottkw.StorCat
```

### Getting Help

1. **Check the main project**: [StorCat GitHub Issues](https://github.com/scottkw/storcat/issues)
2. **Source-specific issues**: [Report here](https://github.com/scottkw/winget-storcat/issues)
3. **winget issues**: [Windows Package Manager GitHub](https://github.com/microsoft/winget-cli/issues)

## 📁 Supported Platforms

This winget source supports:
- **Windows 10** (1809 or later)
- **Windows 11** (all versions)
- **Architecture**: x64 (Intel/AMD 64-bit)

## 🔄 Version Management

### Check current version:
```powershell
winget list scottkw.StorCat
```

### Check for updates:
```powershell
winget upgrade --query scottkw.StorCat
```

### Install specific version (if multiple available):
```powershell
winget install scottkw.StorCat --version 1.1.1
```

## 🧑‍💻 For Developers

### Repository Structure
```
winget-storcat/
├── manifests/
│   └── s/
│       └── scottkw/
│           └── StorCat/
│               └── 1.1.1/
│                   ├── scottkw.StorCat.yaml                 # Version manifest
│                   ├── scottkw.StorCat.installer.yaml       # Installer details
│                   └── scottkw.StorCat.locale.en-US.yaml    # Package metadata
├── update-winget.sh                                        # Automated update script
└── README.md                                               # This file
```

### Testing the source locally:
```powershell
# Clone this repository
git clone https://github.com/scottkw/winget-storcat.git
cd winget-storcat

# Add local source (for testing)
winget source add storcat-local file://./manifests

# Test installation
winget install --source storcat-local scottkw.StorCat
```

### 🚀 Automated Updates

Use the included update script to automatically update manifests when new StorCat releases are published:

```bash
# Run the update script (on macOS/Linux)
./update-winget.sh
```

**What the script does:**
1. **Fetches the latest release** from StorCat GitHub API
2. **Downloads the Windows executable** and calculates SHA256 hash
3. **Updates manifest files** with new version and hash
4. **Validates the manifests** (if winget is available)
5. **Commits changes** with detailed commit message
6. **Optionally pushes** to GitHub

### Manual Updates

To update manifests manually:
1. **Download new release** and calculate SHA256:
   ```bash
   curl -L "https://github.com/scottkw/storcat/releases/download/VERSION/StorCat.VERSION.exe" -o temp.exe
   shasum -a 256 temp.exe
   ```
2. **Update version** in all three manifest files
3. **Update SHA256 hash** in installer manifest
4. **Update release notes** in locale manifest
5. **Test and commit changes**

## 📦 Package Information

- **Package ID**: `scottkw.StorCat`
- **Installer Type**: Portable executable
- **Command**: `storcat`
- **Architecture**: x64
- **Source URL**: `https://github.com/scottkw/winget-storcat`

## 🌐 Related Links

- **Main Project**: [github.com/scottkw/storcat](https://github.com/scottkw/storcat)
- **Releases**: [StorCat Releases](https://github.com/scottkw/storcat/releases)
- **Documentation**: [StorCat README](https://github.com/scottkw/storcat#readme)
- **Report Issues**: [StorCat Issues](https://github.com/scottkw/storcat/issues)
- **Homebrew Tap** (macOS): [homebrew-storcat](https://github.com/scottkw/homebrew-storcat)

## 📄 License

This winget source is licensed under the MIT License - see the main [StorCat LICENSE](https://github.com/scottkw/storcat/blob/main/LICENSE) file for details.

---

<div align="center">
  <p><strong>StorCat winget Source - Windows Package Management Made Easy</strong></p>
  <p>Maintained by <a href="https://github.com/scottkw">Ken Scott</a></p>
</div>