<div align="center">

# 🧊 CryoKernel: msm-5.15 Mirror
**A dedicated, read-only mirror of the CodeLinaro (CLO) msm-5.15 kernel tree.**

![Linux](https://img.shields.io/badge/Linux-5.15-yellow.svg?style=for-the-badge&logo=linux)
![Android](https://img.shields.io/badge/Android-13--17-green.svg?style=for-the-badge&logo=android)
![Mirror](https://img.shields.io/badge/Status-Mirror_Only-blue?style=for-the-badge&logo=github)

</div>

## 📌 About This Repository

This repository serves as a high-speed mirror for the official CodeLinaro (CLO) `msm-5.15` kernel source. It is specifically created and maintained to support the automated CI/CD build process for **CryoKernel** (A custom GKI kernel project).

By hosting the source code directly on GitHub's infrastructure, we bypass the frequent rate limits, bandwidth throttling, and timeout issues commonly experienced when cloning directly from `git.codelinaro.org` inside GitHub Actions workflows.

### 📱 Target Devices (CryoKernel)
This base kernel is used to build custom kernels for the following devices:
* **Redmi Note 12 4G / NFC** (tapas/topaz)
* **Redmi Note 13 4G / NFC** (sapphire/sapphiren)
* **Redmi Pad SE** (xun)

## 🚀 Why Use This Mirror?

* **Lightning Fast CI/CD:** Cloning from GitHub to GitHub Actions runners takes seconds instead of minutes.
* **100% Reliability:** Eliminates build failures caused by `index-pack failed` or remote timeouts.
* **Full History:** Contains the complete branch history necessary for proper Git operations and patching.

## 🛠️ How to Use in GitHub Actions

If you are building a custom kernel based on CLO `msm-5.15` using GitHub Actions, you can point your workflow to this repository instead of the official CLO server.

**Example `git clone` usage in your workflow:**

```yaml
- name: Clone CodeLinaro Source
  run: |
    # Clone from this fast mirror instead of git.codelinaro.org
    git clone --depth=1 -b kernel.lnx.5.15.r1-rel https://github.com/Dyatz/msm-5.15-cryomirror.git msm-5.15
```

## 🔄 Syncing

This repository is synced automatically via GitHub Actions from the upstream CodeLinaro repository using a targeted branch sync. 

* **Upstream:** `https://git.codelinaro.org/clo/la/kernel/msm-5.15.git`

> **Note:** Please do not submit Pull Requests containing kernel modifications directly to this repository. This repo is strictly for mirroring the base CLO tree. All CryoKernel specific features (KernelSU, SuSFS, Kprofiles, etc.) are injected dynamically during the CI build process.

## ⚖️ Credits & Acknowledgements
* **CodeLinaro / Qualcomm:** For the base open-source kernel tree.
* **Linus Torvalds & Contributors:** For the Linux Kernel.