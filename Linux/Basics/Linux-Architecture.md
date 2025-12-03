# Kernel

Understanding these 3 concepts is the foundation of Linux learning.

---

# 1. Linux Kernel
## ✔ What is a Kernel?
The **kernel** is the **core** of the Linux operating system.

The kernel:
- Manages hardware (CPU, RAM, Disk, Network)
- Runs processes(Handles running programs, scheduling, CPU time allocation.)
- File Management (mounts,reads,writes and manages filesytems;ext4,xfs,btrfs)
- Manages memory(Controls RAM usage, swap memory, and allocation for applications.)
- Networking(Handles TCP/IP stack, routing, firewalls, packet flow.)
- Provides system calls for applications

### Types of Linux Kernels
- Monolithic kernel (Linux uses this):Everything runs in kernel space → fast & powerful
- Microkernel :Minimal kernel, rest runs in user space (e.g., Minix).
- Hybrid kernel


 ### ⚙️ Internal Kernel Architecture

Linux kernel itself has five subsystems:


| System Call Interface (SCI) |       


| Process Scheduler |



| Memory Manager (MM) |


| Virtual File System (VFS) |

| Device Drivers |


---

# 2. Bootloader (GRUB)
A **bootloader** is the first program that loads when a computer starts.

### GRUB:GRand Unified Boot Loader (default in most distros)
Functions:
- Select OS to boot (dual boot)
- Load kernel into memory
- Pass parameters to kernel
---

## 2. 🔥Services (Daemon) 

A service (daemon) is a background program that runs continuously.

### Examples:

sshd → handles SSH connections

nginx → web server

mysqld → MySQL database

docker → Docker engine

### Command to manage services:  

####### "systemctl start service" , "systemctl stop service" , "systemctl status service"

## 3. 🔥X Window System (X11)

This is the display system that provides the graphical interface.

### ✔ X11 provides:

windows

mouse

keyboard input

menus

screen drawing

It is the foundation for Linux GUI.

(Current distros may use newer Wayland instead of X11)

## 4. 🔥Desktop Environment 

This is the visual interface you interact with.

### Includes:

panels

icons

file manager

settings

window management

### Examples:

GNOME (default in Ubuntu)

KDE Plasma

XFCE

Cinnamon

➡ This is what makes Linux look like “Windows” to a user.
## 5. 🔥Command Line Interface:
This is the text-based interface where you type commands.

I see something like: <i akash@ubuntu:~$>
CLI is where DevOps engineers work 90% of the time.
## 6. 🔥Shell
The shell interprets the commands you type and sends them to the system.

### Common shells:

bash (most popular)

zsh

fish

sh

## Complete Hierarchy :

          🟦 Desktop Environment (GNOME, KDE)
                  ↑
          🟩 X Window System (X11 / Wayland)
                  ↑
          🟨 Linux Services (sshd, docker, nginx)
                  ↑
          🟧 Shell (bash, zsh)
                  ↑
          🟪 Command Line (Terminal)
                  ↑
          🟥 Linux Kernel (Core of OS)
                  ↑
          💽 Hardware (CPU, RAM, Disk)



## Boot flow:
<img src="https://github.com/akash-infra/Study-Log/blob/a86f7cf6b8293656ce0bd400d9bc35b46d37634e/Linux/Resources/assets/boot.gif" alt="bootflow" width=" 400" height="400">

1. BIOS/UEFI loads  
2. Bootloader (GRUB) starts  
3. GRUB loads Linux Kernel  
4. Kernel starts init/systemd  
5. System boots fully

---

# Summary Table

| Component     | Meaning |
|--------------|---------|
| Kernel       | Core of OS |
| Distribution | Complete OS package around kernel |
| Bootloader   | Program that loads OS on startup |

