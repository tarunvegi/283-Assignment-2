# 283-Assignment-2
Steps followed:
1.	Update the files arch/x86/kvm/vmx/vmx.c and arch/x86/kvm/cpuid.c
2.	Rebuild the kernel using make modules command and make INSTALL_MOD_STRIP=1 modules_install && make install.
3.	Run lsmod | grep kvm to check if the kvm modules are preloaded.
4.	If they are already present remove them using rmmod kvm and rmmod kvm_intel commands.
5.	Run modprobe kvm and modprobe kvm_intel commands to reload edited kvm modules.
6.	Optional- We installed GUI for out Ubuntu host for a friendly UI and ease fo work. Also, we wanted to use Virtual machine manager to created the nested VM. GUI can be enabled on Ubuntu VM using below commands:(ref)
$ sudo apt-get install gnome-shell
$ sudo apt-get install ubuntu-gnome-desktop
$ sudo apt-get install autocutsel
$ sudo apt-get install gnome-core
$ sudo apt-get install gnome-panel
$ sudo apt-get install gnome-themes-standard
7.	Install xrdp through the below commands- we need this to be able to access Ubuntu in GUI mode.
sudo apt-get update
sudo apt-get install -y xrdp
sudo apt-get install -y xfce4
sudo service xrdp restart
8.	Login to the host VM using RDP to have graphical interface.
9.	To enable the kvm module in the host and install necessary packages, run the below commands from host terminal: (ref)
sudo apt install qemu qemu-kvm qemu-system qemu-utils
sudo apt install libvirt-clients libvirt-daemon-system virtinst
10.	Run Virtual Machine Manager and create a new VM inside the host. (download the iso file or guest VM as a prerequisite)
11.	Install Guest OS once the VM is created and login to the nested VM.
12.	Install CPUID using sudo apt install cpuid if it is an Ubuntu VM
13.	Run the command cpuid -l 0x4FFFFFFF to verify the output.
14.	Run the test bash script to produce results and print number of exits.
15.	Run the test2 bash script to produce number of cycles in ebx and ecx registers when eax=0x4ffffffe.
Output screen that verifies that kvm is installed on Ubuntu host
 

Output screen that shows nested VM created on KVM Host
 ![283-1](https://user-images.githubusercontent.com/37550226/205851921-abfc6ef7-16ed-43d9-b4be-0b85d774c330.jpg)
![283-2](https://user-images.githubusercontent.com/37550226/205851923-442d253a-726b-48a4-8d3b-1472656ce467.png)
![283-3](https://user-images.githubusercontent.com/37550226/205851951-427425b0-7670-41ca-8ae3-f4601490019f.png)
 
Output screen that shows number of exits when eax=0x4fffffff
 








