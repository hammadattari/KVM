# KVM (Kernel-based Virtual Machine)
* KVM leverages the Linux kernel and hardware virtualization extensions (Intel VT-x or AMD-V) for near-native performance. 
* lightweight architecture
* Flexibility and cost-effectiveness 
* Stable and mature foundation for various applications
* This allows running virtual machines to be moved between physical hosts without downtime or service interruption.


#  Prerequisites for KVM Installation
* You can check if your CPU supports these extensions by running
    * egrep -c '(vmx|svm)' /proc/cpuinfo
      * For example :The output 8 from the command egrep -c '(vmx|svm)' /proc/cpuinfo indicates that your CPU supports virtualization and that there are 8 logical processors (or cores) capable of hardware virtualization (either Intel VT-x or AMD-V). This means that your system is well-equipped to run KVM (Kernel-based Virtual Machine) and create virtual machines. 
## Steps to Install KVM on Ubuntu

Since your CPU supports virtualization, you can proceed with the installation of KVM on your Ubuntu host. Follow these steps:

1. **Update the Package Repository**:
   ```bash
   sudo apt update
## 2. Install KVM and Required Packages

Install KVM along with the necessary packages:

```bash
sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils

## Verify KVM Installation

After installation, check if KVM is properly installed by running:

```bash
sudo systemctl status libvirtd
## Add Your User to the Necessary Groups

To manage KVM without root privileges, add your user to the `libvirt` and `kvm` groups:

```bash
sudo usermod -aG libvirt $(whoami)
sudo usermod -aG kvm $(whoami)
### QEMU emulator version 
* qemu-system-x86_64 --version

### libvirtd (libvirt) versions
* libvirtd --version <br>
* virt-install --version

