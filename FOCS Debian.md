## How to install FOCS Debian

Authored by: Wang Yunchen <mac-wang@sjtu.edu.cn>

Authored by: Bunyod Suvonov <b.suvonov@sjtu.edu.cn>

---

### Notes

This guide assumes that you are installing FOCS Debian by using VMware. However, the installation process is pretty much the same regardless of whether you install in VirtualBox or on your own computer. Please refer to the corresponding documents for details. Platform-specific (VMware, VirtualBox, dual boot) instructions would also be mentioned in this document if the authors deem it necessary, so read through both documents before you begin your installation and ask for clarification if in trouble.

---

## Premable

FOCS Debian is a Debian distribution. It is designed by and for fellow JIers. It features the *K Desktop Environment* by default, a desktop environment that mimics the look and feel of Windows, yet remains highly customizable. It also have software repositories for common software including VSCode and Mattermost preconfigured, such as to provide a non-disturbing experience for users new to Linux. You can try out FOCS Debian directly from a USB stick before installing it, then you can install it on your computer as your daily operating system. This guide will guide you through the installation of FOCS Debian.

## Linux Installation

#### Install VMware Player if you haven't done so

VMware Player is free for non-commercial use. You may download a copy of VMware player at https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html.

#### Fetch FOCS Debian ISO image

FOCS Debian ISO image is available at https://focs.ji.sjtu.edu.cn/debian/debian-ji_0.0.1_amd64.iso.

If you want to burn it into a USB stick to install on your computer, you need a USB stick of at least 8 GB in size. 

#### Enable Windows Hypervisor Platform if you are on Windows 11 or using WSL

*If you're on an old Windows 10 computer, or if you want to install on your physical computer, you can safely skip this step*

If you're using Windows 11, you have Hyper-V setup on your system. Hyper-V and VMware are incompatible; you need to enable Windows Hypervisor Platform in order to use VMware alongside with Hyper-V.

In *Settings*, under *Apps* -> *Optional Features*, click on *More Windows Features* in the bottom (Win11) or on the right (Win10)

![windows-features](/home/mack/Documents/Linux Party/VE280 Tutorials/images/features.png)

Check **Windows Hypervisor Platform**. Reboot your computer.

Note that this step is also necessary if you want to install FOCS Debian on VirtualBox.

#### Create a new Virtual Machine

- In a new VMware Player window, click on "Create a new Virtual Machine"

- Select the FOCS Debian ISO you just downloaded. Click Next.

- Under "Select a Guest Operating System", choose "Linux" and "Debian 11.x 64-bit".

- Enter a name for your VM.

- It's recommended to adjust the hardware settings. At least 20 GB of hard disk, 4 GB of memory and 8 processor cores are recommended. The more you give memory and processor cores, the better the performance will be.

  The VM will automatically power on when you finish the wizard.

#### Install FOCS Debian

- You will be greeted by a fancy desktop once the VM boots up.

![image-20230922013743881](images/debian_greeting.png)

​	If you are installing FOCS Debian in a physical machine, you may now play around with FOCS Debian without making changes to your computer.

- Once you decide to install FOCS Debian, go to *System* -> *Install System* in the Start Menu.

![image-20230922014033089](images/installer.png) 

- We **recommend you to stick to English during installation**. You can change system language to Chinese afterwards. The main rationale for this is to avoid Chinese folder names, which will stop some apps working.

- Proceed to the "Partitions" page.

  - If you are on a physical machine, the installer offers a option to re-partition your existing disks for you. 

    You will not lose your existing Windows system when accepting the installer's solution.

    You can choose to accept what the installer proposes, or select "Manual partitioning" to adjust by yourself.

    Be careful when you choose to repartition by yourself. Reach to us if you're unsure.

  - If you are in a virtual machine, you may safely select "Erase disk".

- Enter your personal information on the next page. Note that **no Chinese is allowed in the login name**.

- Click Install to begin installation. Depending on the performance of your computer it may last for several minutes.

- Reboot when finishing, remove the USB stick when proposed (if you are installing on your disk)



#### Welcome to your new Linux world!

If you installed FOCS Debian on your physical computer and want to return to Windows, reboot your computer and navigate to "Windows Boot Manager" in the boot manager. You need to press system specific key when you turn on your computer to enter the boot menu.

#### FAQ after installation

- The performance of the Virtual Machine is not satisfiable.

  - Try to increase more memory or allocate more processor cores in VM settings. 
    - In VMware this is pretty straightforward.
    - In VirtualBox, you need to navigate to *System* under VM settings. You can increase more memory there. You also need to navigate to *System* -> *Processor* to increase processor core count, and enable Nested Paging under *System* -> *Acceleration*.

- I want to open folders with double click instead of single click.

  - You can change it in the following section (:

    ![image](https://github.com/Bunyod-Suvonov/FOCS_Debian_Install_Guide/assets/109164894/330341c4-007f-4ebe-8cd2-3ce410b3640f)


- The icons, mouse cursor, text... is too small!

  - Change display scale factor here:

  ![image-20230922020615633](images/scale_factor.png)

  - Change mouse cursor size in System Settings:

    ![image-20230922020800446](images/cursor.png)

  
  - Right click on the taskbar to adjust its height.
  
- I can't modify my Windows files!

  - Return to your Windows, launch an *Administrator Windows Powershell*, and type the command `powercfg /h off` there.
