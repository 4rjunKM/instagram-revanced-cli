<div align="center">

# Instagram ReVanced CLI Patcher

Professional command-line workflow for patching Instagram using ReVanced CLI.

Lightweight, reproducible, and developer-focused setup designed for automation and manual control over patch execution.

<br>

[<img src="https://img.shields.io/badge/Get%20Releases-GitHub-black?logo=github&style=for-the-badge"
alt="Get it on GitHub"
height="45">](../../releases)

[<img src="https://github.com/user-attachments/assets/713d71c5-3dec-4ec4-a3f2-8d28d025a9c6"
alt="Get it on Obtainium"
height="80">](https://apps.obtainium.imranr.dev/)

</div>

---

## Overview

This project provides a clean CLI-based process to apply supported ReVanced patches to Instagram.
It is intended for users who prefer transparent builds instead of GUI patchers.

The workflow focuses on:

* Manual APK input
* Controlled patch selection
* Clean terminal logging
* Reproducible developer builds

---

## Requirements

Before starting, ensure the following are installed:

* Java (JDK 17 or newer)
* Windows Command Prompt or PowerShell
* Latest `revanced-cli.jar`
* Latest `revanced-patches.jar`

Download official tools manually and place them locally.

---

## Patching Instructions

### 1. Prepare the APK

Download a compatible Instagram APK version.

Rename it:

```
instagram.apk
```

Place it inside your local `input` directory.

---

### 2. Configure Enabled Patches

Edit `patches.json` and include only patches compatible with Instagram.

Example:

```json
{
  "patches": [
    "Hide ads",
    "Disable analytics",
    "Sanitize sharing links"
  ]
}
```

To list available patches:

```
java -jar tools\revanced-cli.jar list-patches -b tools\revanced-patches.jar
```

---

### 3. Run Patch Command

Execute the build script or run manually:

```
java -jar tools\revanced-cli.jar patch ^
 -b tools\revanced-patches.jar ^
 -o Output.apk ^
 -p patches.json ^
 input\instagram.apk
```

If successful, the patched APK will be generated as:

```
Output.apk
```

---

## Understanding Patch Logs

During execution you may see messages such as:

```
INFO: "Hide ads" succeeded
SEVERE: "Remove build expired popup" failed
```

Explanation:

* **INFO succeeded** → Patch applied correctly.
* **SEVERE fingerprint error** → Patch does not match current APK version.

Instagram updates frequently, so some patches may temporarily fail.
A failed patch does not always stop the build process.

Recommended approach:

* Use a supported APK version.
* Keep patches updated.
* Remove incompatible patches from configuration if needed.

---

## Installation

1. Transfer the generated APK to your Android device.
2. Install manually.

If installation fails:

* Uninstall the original Instagram app first.
* Ensure signatures are compatible.

---

## Obtainium Support

This project can be tracked using Obtainium for update monitoring.

Add the GitHub repository link inside Obtainium to receive future release notifications.

---

## Notes

* APK files are intentionally not included.
* This project only contains automation scripts and configuration.
* No proprietary binaries are distributed.

---

## Disclaimer

This project is provided for educational and personal automation purposes only.
The author does not distribute proprietary applications or modified binaries.
