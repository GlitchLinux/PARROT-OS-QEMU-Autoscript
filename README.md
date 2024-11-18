PARROT-OS-QEMU-Autoscript

This Bash script automates the process of downloading, configuring, and running a bootable Ventoy image with PARROT OS. It includes downloading Ventoy, formatting a virtual disk image, adding the PARROT OS ISO, and running the setup in a QEMU virtual machine.

Features
Downloads and extracts the specified version of Ventoy.
Formats a virtual disk image using Ventoy with exFAT/MBR.
Downloads PARROT OS and prepares it on the Ventoy partition.
Launches a QEMU virtual machine with the Ventoy image.
Cleans up temporary files after execution.

Dependencies:
Ensure the following dependencies are installed:
wget - for downloading files.
tar - for extracting Ventoy files.
dd - for creating the virtual disk image.
losetup - for managing loop devices.
mount - for mounting the Ventoy partition.
qemu-system-x86_64 - for running the virtual machine.
Root permissions (run the script as root).

Download & Execution:
(Run the script as root)
```bash
git clone https://github.com/GlitchLinux/PARROT-OS-QEMU-Autoscript.git
cd PARROT-OS-QEMU-Autoscript
sudo bash PARROT-OS-QEMU-Autoscript.sh
```
What it does:
Checks for root privileges: The script must be run as root to perform disk operations.
Deletes /tmp contents: Clears /tmp except for the script itself.
Downloads Ventoy and PARROT OS:
Ventoy version: 1.0.96
PARROT OS version: 6.2
Formats a virtual disk image:
Creates a 3GB .img file.
Configures it with Ventoy.
Prepares the Ventoy partition:
Mounts the exFAT partition.
Copies the PARROT OS ISO to the partition.
Runs QEMU virtual machine:
Launches the VM with KVM acceleration and 2GB of RAM.
Cleans up:
Removes temporary files in /tmp after VM execution.
Notes
Ensure you have sufficient privileges and free space in /tmp.
The script is tested for Ventoy 1.0.96 and PARROT OS 6.2. For other versions, modify the ventoy_version and iso_url variables.
Temporary files are created in /tmp and deleted after the script finishes.
Disclaimer
This script is provided "as is" without any warranty. Use at your own risk. Always double-check the operations involving your system and storage devices.

License
This project is licensed under the MIT License. See the LICENSE file for details.
