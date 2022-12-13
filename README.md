# 283-Assignment-2&3

 For each member in your team, provide 1 paragraph detailing what parts of the lab that member 
implemented / researched. (You may skip this question if you are doing the lab by yourself).

I have done it alone professor


 Describe in detail the steps you used to complete the assignment. Consider your reader to be someone 
skilled in software development but otherwise unfamiliar with the assignment. Good answers to this 
question will be recipes that someone can follow to reproduce your development steps.

Steps are explained below professor



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
         
      Output screen that verifies that kvm is installed on Ubuntu host.                                                   ![283-1](https://user-images.githubusercontent.com/37550226/205851921-abfc6ef7-16ed-43d9-b4be-0b85d774c330.jpg)

Output screen that shows nested VM created on KVM Host                            
![283-2](https://user-images.githubusercontent.com/37550226/205851923-442d253a-726b-48a4-8d3b-1472656ce467.png)


 
 
 
Output screen that shows number of exits when eax=0x4fffffff ![283-3](https://user-images.githubusercontent.com/37550226/205851951-427425b0-7670-41ca-8ae3-f4601490019f.png)


Assignment-3
I had done it alone.

fisrtly, Go to the assignment 2 setup VM

Then, update cpuid.c and vmx.c as per the desired requirements

Thn use the following command "make -j 8 modules", (8 is number of CPU's, I have 8 in my VM. Find CPU's using "nproc" command)

Then use command "make -j 8".

Late, use command "sudo make INSTALL_MOD_STRIP=1 modules_install".

Then, Reboot the VM using a "sudo reboot"

Later, open the Virtual Machine created using virtual manager.

Then, create test.c file and run it to get required output.

Later, on the frequency of exits – does the number of exits increase at a stable rate? Or are there more exits performed during certain VM operations? Approximately how many exits does a full VM boot entail?

Here, 5116977 number of exits are not stable and keeps changing.

-> Of the exit types defined in the SDM, which are the most frequent? Least?

Exit 48:EPT Violation, Exit 1: External Interrupt, Exit 30: IO Interrupt, Exit 32:WRMSR -> Most Frequently occuring. Exit 29: MOV DR, Exit 46: Access to IDTR, Exit 55 XSETBV -> Least Frequently occuring.
 

![Img4](https://user-images.githubusercontent.com/37550226/207257912-bffc08e9-d637-4c6b-b790-27667fc3d6f2.jpeg)
![Img3](https://user-images.githubusercontent.com/37550226/207257918-1724f027-65a4-4326-9b09-95e953ff8494.jpeg)
![Img2](https://user-images.githubusercontent.com/37550226/207257920-870afa63-d4bd-4115-935d-ad1eef3277b7.jpeg)
![Img1](https://user-images.githubusercontent.com/37550226/207257924-54f63af9-a589-4f37-b9c9-33e5610c0764.jpeg)

 








