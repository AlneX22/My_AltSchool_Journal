# Week 2-3 - Second Semester Month 1 CLE 520

## 🗓️ Week Topic: Introduction And Deep Dive Into Linux Operation System

---

## ✅ Topics Covered

  **Week[2]**

- Operating Systems
- Linux
- Setting Up Linux OS
- Linux Shell
- Linux Commands
- Linux Commands(File Operation)
- Linux Commands (Text Editors)
- Linux Commands (Seeking Help)

---

  **Week[3]**

- Users & Groups
- Managing Groups
- File Permissions
- SSH

---

## 💡 What I Learned
- I now understand that an **OS** (Operating System) is a software which acts as an interface between the end user and computer hardware. 
- And there are different categories of Operating System in computer and other devices which are: 
  - **Batch Operating System**
  - **Multitasking/Time Sharing OS**
  - **Multiprocessing OS**
  - **Real Time OS**
  - **Distributed OS**
  - **Network OS & Mobile OS**
- Personal Computer Operating Systems were first developed in the late 1950s to manage tape storage.
- An **OS** works as an intermediate between the user and computer. It helps the user to communicate with the computer without knowing how to speak the computer’s language.
- The kernel is the central component of a computer operating systems. The only job performed by the kernel is to the manage the communication between the software and the hardware.
- Two most popular kernels are **Monolithic** and **MicroKernels**
- Process, Device, File, I/O, Secondary-Storage, Memory management are various functions of an Operating System.
- I also learned about the **UNIX** being the first developed in the 1960's and the **UNIX-like (Sun Solaris, GNU/Linux, and MacOS X )** operating system. With Linux in its turn is packaged in a form known as linux distribution. there are several distributions both free and commercial.
- The UNIX operating system is made of **Three(3)** parts
  - **The Kernel:** Is the hub of the perating system. it allocates time and memory to programs and handles the file store and communication in response to system calls.
  - **The Shell:** Acts as an interface between the user and the kernel
  - **The Process:** Is an executing program identified by a unique **PID (process identifier).**
- Everyhting in UNIX is either a file or a process.
- All files are grouped together in the directory structure, and is arranged in a hierarchial structure, like an inverted tree with the top of the hierarchy called **root**
- The different distribution installation hosts of the Linux Operating system **(BareMetals, Virtual Machines, Containers)**
- The installation Hosts **(Virtual Machines):** **VirtalBox, VMWare, Parallels, Hyper-V, Qemu, Citrix**
- Distributon Mediums: **CD/DVDs,ISO Images, Clones, Virtual Machine Images, Container Images, Source Code**
- where to get OS Images: **OS Project website, Code hosting platforms(e.g. GitHub), Community forums, A friend of a friend, Registries**
- Types of Linux Shell: **sh (Bourne shell), Bash (Bourne-again Shell), Korn Shell(ksh), zsh.**
- Also looked at the different linux commands and their uses:
  - **pwd:** Present Working Directory
  - **cd DIR:** Moves you into a directory
  - **ls:** lists the content of a directory
  - **uname -a:** Identify what type of operatng system you are using
  - **date:** Check system date and time
  - **uptime:** Know how long the system has been on
  - **whoami:** Know who is currently logged in
  - **export VAR=VALUE:** Set a variable in the terminal 
  - **echo $VAR:** Display the content of the variable
  - **ps:** View running application
  - **top:** Get detailed info about the processes that are running 
  - **df -h:** Tells you more about the storage that you have
  - **id:** show user ID and group
  - **free -h:** Ram usage
  - **mkdir DIR:** create a new direct 
  - **touch FILE:** Create an empty file
  - **cp FILE FILE:** Copy files between different locations safely
  - **mv FILE FILE:** Cut and paste(move a file) or Remane a file
  - **rm FILE:** Delete a file
  - **cat FILE:** Display the content of a file
  - **head FILE:** Display the top of the file
  - **tail FILE:** Display the buttom or better put the end of a file
  - **vim FILE:** Opens a text editor called **vim** for editing files
  - **nano FILE:** Open a simpler text editor **nano** within you terminal to edit files
  - **man COMMAND:**  Gives you detailed information about a command
  - **COMMAND -h:** Gives a quicker reference of a command
  - **COMMAND -help:** Also gives a quicker reference of a command
- Had a better understanding how the linux system works with users & groups and how to manage them with the following commands
  - **cat /etc/passwd:** Contains the users stored in the linux machine 
  - **adduser [username]:** Adds user
  - **passwd [username]:** Set password for user
  - **addgroup [groupname]:** Adds group
  - **usermod -ag [groupname] [username]:** Adds user to group
  - **groupmod -n [newname] [groupname]:** Rename a group
  - **usermod -aG sudo [username]:** Add user to sudoers file
  - **cat /etc/group:** Contains list of all groups
  - **id username:** Confirms user IDs
  - **adduser -s /user/bin/zsh username:** Create user with a specific shell
  - **groupdel [groupname]:** Delete a group
  - **userdel [username]:** Delete a user
- Also learnt about **File permissions** after learning about users and groups because every file or directory belongs to a certain **user or group**. when you list file with **ls** it shows you the owners and permissions on a file.
- First the **chown** command is used to set which user should own a file 
  - **chown [user]:[group] [FILENAME]:** change ownership of a file
  - **chmod [options] [FILENAME]:** change the file permission
- There are different ways to set permissions. **Symbolic mode and Numeric mode**
- With the **Symbolic method** you use the **target user, actions and permissions** to set the neccesary permissions you want.
  - Actions are **+(add), -(remove), =(replace)**
  - Permissions can be **r(Read), w(Write), x(Execute)**
  - Target User **u(Owner), g(Group), o(Other users), a(All users)**
- For the numeric method, you can calculate the permissions for a user using 
  - **4(Read), 2(Write), 1(Execute), --o(No permission).** For Example **chmod 750 dirname** **(7 for the Owner, 5 for the Group, & 0 for Others)**
  - **chmod [Numeric Notation] [FILENAME]:** Change file Permission wih numeri notation
- Other commands for permission change 
  - **setfacl -m u:[user]:[permission] FILENAME:** Assign different permissions to users.
  - **chmod g=r [FILENAME]:** Give members of the group permissions to read the file
  - **chmod a-x [FILENAME]:** Remove execute permissions for all users
  - **chmod -R o-w [dirname]:** Recursivelly remove the write permission for other users
  - **chmod og-rwx [FILENAME]:** Remove the read, write and execute permission for all users except file owners
  - **chmod og= [FILENAME]:** Remove the read, write and execute permissions for all users except file owner
- With **stat -c "%a" [FILENAME]** you can check the file permission in numeric notation.
- Also learnt about Authentication specifically with **SSH (Secure Shell)** used for remotely acessing your server. it is an authentication methond that is used by using **private & public key pairs** and it ususally comes installed with alot of linux operating systems, but you can always install it by installing the application called **Open SSH**
  - Private keys are always kept in the local machine
  - Public keys can be shared with Sys Admis to add to co-operate servers or used in some form of authentication to give you access
  - Public keys are stored in the **authorized_key** file on server
  - You can generate **SSH Key ** using the command **SSH -keygen** and they are stored in the **/home/$user/.ssh.** 
---

## 😓 Challenges
- I'm still trying to fully understand the symbolic mode of permissions and how to use the diffeent actions with it.

---

## 🧪 Practicals or Projects
- Installed Ubuntu on my laptop(BareMetal) using the ISO file burned into a bootable flashdrive.
- Logged into a remotely hosted linux machiche which i created with the cloud provider **AWS** also called an **EC2 instance** in AWS via SSH from my local linux machine.
- Created 3 groups – and added the admin group to sudoers.
- Created a user in each of the groups. 
- Generated SSH Keys for the users
- Created a file as a root user and gave each user different permissions to the file i created
- studied other linux commands 
---

## 🔗 Resources Used
- https://www.guru99.com/operating-system-tutorial.html
- https://www.tutorialspoint.com/operating_system/os_overview.htm
- https://www.hpc.iastate.edu/guides/unix-introduction
- https://en.wikipedia.org/wiki/Unix
- https://www.fosslinux.com/44623/top-unix-based-operating-systems.htm
- https://www.redhat.com/en/topics/linux/what-is-the-linux-kernel
- https://opensource.com/article/21/8/linux-kernel
- https://developer.ibm.com/articles/l-linux-kernel/
- https://www.guru99.com/linux-commands-cheat-sheet.html
- https://www.linuxtrainingacademy.com/linux-commands-cheat-sheet/
- https://devhints.io/vim
- https://linuxize.com/post/how-to-create-users-in-linux-using-the-useradd-command/
- https://linuxize.com/post/how-to-delete-group-in-linux/
- https://www.w3resource.com/linux-system-administration/groups.php
- https://linuxize.com/post/chmod-command-in-linux/
