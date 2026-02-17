<div align="center">

# Instagram ReVanced CLI Patcher

Professional command-line workflow for patching Instagram using ReVanced CLI.

Lightweight, reproducible, and developer-focused setup designed for automation and manual control over patch execution.

</div>

---

## Overview

This project provides a clean CLI-based process to apply supported ReVanced patches to Instagram.
It is intended for users who prefer transparent builds instead of GUI patchers.

The goal is to keep the workflow minimal:

* Manual APK input
* Controlled patch selection
* Clear logging during build

---

## Requirements

Before starting, ensure the following are installed:

* Java (JDK 17 or newer)
* Windows Command Prompt / PowerShell
* Latest `revanced-cli.jar`
* Latest `revanced-patches.jar`

Download official tools from their respective sources and place them locally.

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

This is common because Instagram updates frequently.
A failed patch does not always stop the build process.

Recommended approach:

* Use a supported APK version.
* Update patches regularly.
* Remove incompatible patches from configuration if needed.

---

## Installation

1. Transfer the generated APK to your Android device.
2. Install manually.

If installation fails:

* Remove the original Instagram app first.
* Ensure signatures are compatible.

---

## Notes

* APK files are intentionally not included.
* This project only provides automation scripts and configuration.
* Users are responsible for maintaining legal and ethical usage.

---

## Disclaimer

This project is provided for educational and personal automation purposes only.
The author does not distribute proprietary applications or modified binaries.
