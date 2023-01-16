!!! LACK OF TESTING, Please test and feedback.

!!! WARNING: Do not use in production environment.


# Realtek RTL8125 NIC driver for ESXi 7.0.3

This source code is based on realtek official source, VMware-ESXi-70U3-ODP and VMware-TOOLCHAIN-ODP-70U3.

Just do these steps:
- Prepare the building environment, I did it on CentOS 7
- Log in with root, make a folder name 'build' on /, make folder toolchain and vsphere in /build.
- untar tar -xvf /<realpath>/VMware-TOOLCHAIN-ODP-70U3/tc-src.tar to /build/toolchain/
- Compile the toolchain, dest path is /build/toolchain/lin64
- Extract and copy vmkdrivers-gpl from 70U3-ODP to /build/vsphere
- Copy build-r8125.sh to /build/vsphere/vmkdrivers-gpl/
- Copy r8125 folder to /build/vsphere/vmkdrivers-gpl/vmkdrivers/src_9/drivers/net
- Run build-r8125.sh

# Realtek PCIe FE / GBE / 2.5G / Gaming Ethernet Family Controller Software

- https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-pci-express-software

# VMware vSphere Hypervisor (ESXi) 7.0U3d Open Source Information

- https://customerconnect.vmware.com/downloads/details?downloadGroup=ESXI70U3D_OSS&productId=974

## Open Source Disclosure packages for VMWare vSphere Hypervisor (ESXi) 7.0U3d

Open Source Disclosure Package for VMware vSphere Hypervisor (ESXi) 7.0 U3 (VMware-ESXi-70U3-ODP.iso)

https://download3.vmware.com/software/vsphere70U3/open-source/VMware-ESXi-70U3-ODP.iso

## Open Source Disclosure Package for VMWare vSphere Hypervisor (ESXi) 7.0 U3 Toolchain

TOOLCHAIN packages, contains all the used toolchains during the build process, together with source, build instructions and build scripts.

Open Source Disclosure Package for VM...phere Hypervisor (ESXi) 7.0 U3 Toolchain (VMware-TOOLCHAIN-ODP-70U3.iso)

https://download3.vmware.com/software/vsphere70U3/open-source/VMware-TOOLCHAIN-ODP-70U3.iso

# test

`
esxcli software vib remove -n net-r8125
esxcli software vib install -v /vmfs/volumes/datastore1/net-r8125-9.006.04-1.vib
`

