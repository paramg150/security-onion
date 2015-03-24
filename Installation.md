# Welcome to the Security Onion Installation Guide! #

To install Security Onion, you're going to either install our Security Onion ISO image **or** install a standard Ubuntu 12.04 ISO image and then add our Security Onion PPA and packages.  **Please keep in mind that our PPA and packages are only compatible with Ubuntu 12.04**.

# ALWAYS verify the checksum of ANY downloaded ISO image #
Regardless of whether you're downloading our Security Onion ISO image or whether you're starting with an Ubuntu 12.04 ISO image, you should ALWAYS verify the checksum of the downloaded ISO image.
  * If downloading our Security Onion ISO image, you can download the accompanying .md5 file or you can use the MD5/SHA1 checksums that Sourceforge displays when clicking the Information (view details) button to the right of the ISO image (it's a circle with an "i").
  * If downloading an Ubuntu 12.04 ISO image, use the accompanying .md5 file.
Here are some Ubuntu instructions for verifying checksums:
https://help.ubuntu.com/community/HowToMD5SUM

# Hardware #
If you haven't already, please review the [Hardware](Hardware.md) page.

# UEFI #
If you have a new machine with UEFI, please see:
https://help.ubuntu.com/community/UEFI

# Choose your Installation Guide #
We have different Installation Guides to cover various use cases.  Please choose the appropriate Installation Guide for your use case.

## Quickly Evaluating Security Onion ##
If you just want to **quickly evaluate** Security Onion, choose one of the following.  If you're a first time user, please choose the first option.

  * [Download our Security Onion ISO image and Quickly Evaluate](QuickISOImage.md)
OR
  * [Quickly Evaluating Security Onion using \*your preferred flavor of Ubuntu 12.04\*](InstallingOnUbuntu.md)

## Production Deployment ##
If you're deploying Security Onion in **production**, please see:
  * [Production Deployment](ProductionDeployment.md)