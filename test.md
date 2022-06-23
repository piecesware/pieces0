# <a id="span-212-157"></a>[How to Get the Size of a Directory in Linux](https://phoenixnap.com/kb/show-linux-directory-size)

<a id="span-215-157"></a>May 15, 2020

<a id="span-217-157"></a>[commands](https://phoenixnap.com/kb/tag/commands)[linux](https://phoenixnap.com/kb/tag/linux)

[Home](https://phoenixnap.com/kb/) » [SysAdmin](https://phoenixnap.com/kb/category/sysadmin) » How to Get the Size of a Directory in Linux

<a id="ftwp-header-title"></a>Contents

<a id="span-87-157"></a>

Introduction

Many users run Linux from the command line. However, the command line - sometimes known as the terminal - doesn’t have an intuitive interface for [checking disk space in Linux](https://phoenixnap.com/kb/linux-check-disk-space).

**This guide shows you how to find the size of a specific directory in Linux from the command line.**

<img width="752" height="376" src=":/5801e31f3c7b44eca37795e009ebcf4c"/>

Prerequisites

- A system running Linux
- A command line / terminal window (available by clicking Search, then typing **terminal**)
- A user account with **sudo** or **root **privileges

**Note:** In Linux, a **directory** is the equivalent of a folder in Windows. A directory may have directories inside (called **subdirectories**), or it may only contain files.

## Option 1: Display the Size of a Directory Using the du Command

The **`du`**command stands for disk usage. This command is included by default in most Linux distributions.

You can display the size of your current directory by typing **`du`** in the command line:

```
du
```

The system should display a list of the contents of your home directory, with a number to the left. That number is the size of the object in kilobytes.

![An example of the du command output.](:/a059ebd843174fd0b138763308882ffd)

You can add the **`-h`** option to make the output more readable:

```
du -h
```

![Readable list of contents of your home directory.](:/957a009fd027457eb539877113891478)

Each entry will start with a number and a letter. The number is the amount of space used, and the letter (usually K, M, or G) indicates Kilobytes, Megabytes, or Gigabytes. For example:

```
400K – 400 kilobytes
7.3M – 7.3 megabytes
2.2G – 2.2 gigabytes
```

To **find the size of a specific directory different from your current working directory**. The **`du`** command allows you to specify a directory to examine:

```
du -h /var
```

This displays the size of the contents of the **/var** directory. You may see some entries with an error, as in the image below.

![Display the size of a specific directory.](:/083df4630c184e949d956726255c4e75)

This happens when your user account does not have permission to access a particular directory. Use the **`sudo`** or **`su`** command to get access privileges:

```
sudo du -h /var
```

**Note:** Some versions of Linux don’t enable **`sudo`** by default. You can use the **`su`** command to switch to the **root** user account instead.

To display total disk usage of a particular directory, use the **`-c`** command:

```
sudo du -c /var
```

Options can be combined. If you wanted to repeat the previous command in human-readable format, enter the following:

```
sudo du -hc /var
```

You can limit the scan to a certain level of subdirectory by using the max-depth option. For example, to scan only the size of the top directory, use **`--max-depth=0`**:

```
sudo du -hc --max-depth=0 /var
```

If you wanted to list only the top directory and the first layer of subdirectories, change **`--max-depth=1`**:

```
sudo du -hc --max-depth=1 /var
```

![Find the size of the top directory](:/7510ab58793d4acabe58c388303fa5ef)

If you run into trouble or want to explore more options for the **`du`** command, enter the following command to display the help file:

```
man du
```

## Option 2: Get Size of Directory in Linux Using tree Command

By default, the **`tree`** command is not included in some versions of Linux. To install it, enter the following:

- For Debian / Ubuntu

```
sudo apt-get install tree
```

- For CentOS / RedHat

```
sudo yum install tree
```

The **`tree`** command displays a visual representation of your directories. It uses lines to indicate which subdirectories belong where, and it uses colors to indicate directories and files.

**`tree`** can also be used with options. To display a human-readable size of the current directory’s subdirectories, enter the following:

```
tree -d -h
```

![Display disk usage using the tree command.](:/5fe9178600d44378a81f7dad29192972)

Like the **`du`** command, **`tree`** can target a specific directory:

```
tree /var
```

This command takes a few moments since the **/var** directory has many entries.

The **`tree`** command also has a help file, which you can access by entering:

```
man tree
```

## Option 3: Find the Size of a Linux Directory Using ncdu Command

The **ncdu** tool stands for **NCurses Disk Usage**. Like the **`tree`** command, it is not installed by default on some versions of Linux. To install it, enter the following:

- For Debian / Ubuntu

```
sudo apt-get install ncdu
```

- For CentOS / RedHat

```
sudo yum install ncdu
```

The **`ncdu`** utility is an interactive display of your disk usage. For example, enter the following:

```
ncdu
```

![Display Disk Usage Using the ncdu command.](:/279cead6502c4f97aa9f1b893e5e4882)

In the upper left corner, it displays the current directory being scanned. A column on the left displays the numerical size, a graph of **`#-`** signs to indicate the relative size, and the file or directory.

Use the up and down arrows to select different lines. The right arrow will browse into a directory, and the left arrow will take you back.

**`ncdu`** can be used to target a specific directory, for example:

```
ncdu /var
```

For help, press the **`?`** key inside the **ncdu interface**. To quit, press the letter **`q`**.

**Note:** Learn how to [move directories in Linux](https://phoenixnap.com/kb/move-directory-linux) using the GUI or system commands.

Conclusion

You now have three different options to find the size of a directory in Linux operating systems.

If you want to learn more about directories in Linux, read our article how to [rename directories in Linux](https://phoenixnap.com/kb/rename-directory-linux).

Was this article helpful?

YesNo

[Share on Twitter](https://twitter.com/intent/tweet?text=How%20to%20Get%20the%20Size%20of%20a%20Directory%20in%20Linux&url=https%3A%2F%2Fphoenixnap.com%2Fkb%2Fshow-linux-directory-size) [Share on Facebook](https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fphoenixnap.com%2Fkb%2Fshow-linux-directory-size) [Share on LinkedIn](https://www.linkedin.com/shareArticle?mini=1&url=https%3A%2F%2Fphoenixnap.com%2Fkb%2Fshow-linux-directory-size&title=How%20to%20Get%20the%20Size%20of%20a%20Directory%20in%20Linux&source=https%3A%2F%2Fphoenixnap.com%2Fkb&summary=Use%20the%20command%20line%20interface%20to%20display%20directory%20size%20and%20for%20display%20disk%20space.%20This%20guide%20will%20help%20you%20find%20the%20amount%20of%20disk%20space%20used%20by%20any%20given%20directory.) [Share on Email](mailto:?body=I%20read%20this%20post%20and%20wanted%20to%20share%20it%20with%20you.%20Here%27s%20the%20link%3A%20https%3A%2F%2Fphoenixnap.com%2Fkb%2Fshow-linux-directory-size&subject=A%20post%20worth%20sharing%3A%20How%20to%20Get%20the%20Size%20of%20a%20Directory%20in%20Linux)

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)

<a id="span-100-157"></a>Sofija Simic

<a id="span-107-157"></a>Sofija Simic is an aspiring Technical Writer at phoenixNAP. Alongside her educational background in teaching and writing, she has had a lifelong passion for information technology. She is committed to unscrambling confusing IT concepts and streamlining intricate software installations.

Next you should read

[SysAdmin](https://phoenixnap.com/kb/category/sysadmin) [Web Servers](https://phoenixnap.com/kb/category/web-servers)

[Linux Commands Cheat Sheet: With Examples](https://phoenixnap.com/kb/linux-commands-cheat-sheet)

February 21, 2020

* * *

A list of all the important Linux commands in one place. Find the command you need, whenever you need it or...

[Read more](https://phoenixnap.com/kb/linux-commands-cheat-sheet)

[SysAdmin](https://phoenixnap.com/kb/category/sysadmin)

[How to Check Disk Space in Linux](https://phoenixnap.com/kb/linux-check-disk-space)

April 13, 2020

* * *

This tutorial shows how to display disk usage from a command line in Linux. It is important to know how much...

[Read more](https://phoenixnap.com/kb/linux-check-disk-space)

[Backup and Recovery](https://phoenixnap.com/kb/category/backup-and-recovery) [SysAdmin](https://phoenixnap.com/kb/category/sysadmin)

[How to Use fsck Command to Check and Repair Filesystem](https://phoenixnap.com/kb/fsck-command-linux)

May 14, 2020

* * *

If you want to keep your filesystems clean and without errors, you need to scan it on regular basis. In this...

[Read more](https://phoenixnap.com/kb/fsck-command-linux)

[SysAdmin](https://phoenixnap.com/kb/category/sysadmin) [Web Servers](https://phoenixnap.com/kb/category/web-servers)

[How To Customize Bash Prompt in Linux](https://phoenixnap.com/kb/change-bash-prompt-linux)

May 12, 2020

* * *

Follow this article to learn how to make changes to your BASH prompt. The guide shows how to edit the bashrc...

[Read more](https://phoenixnap.com/kb/change-bash-prompt-linux)

- [![](:/df041b48bbfe424bbaa3c1b1a1c54840)](https://phoenixnap.com/servers/flexservers?utm_source=banner-internal&utm_medium=banner&utm_campaign=flexservers-saas2021)
    

- Recent Posts
    
- - [Flatpak vs. Snap vs. AppImage](https://phoenixnap.com/kb/flatpak-vs-snap-vs-appimage "Permalink to Flatpak vs. Snap vs. AppImage")
    - [Kubernetes Networking Guide {Definition & How to Implement}](https://phoenixnap.com/kb/kubernetes-networking "Permalink to Kubernetes Networking Guide {Definition & How to Implement}")
    - [Kubernetes Service Discovery Guide](https://phoenixnap.com/kb/kubernetes-service-discovery "Permalink to Kubernetes Service Discovery Guide")
    - [Portainer vs. Rancher: In-depth Comparison](https://phoenixnap.com/kb/portainer-vs-rancher "Permalink to Portainer vs. Rancher: In-depth Comparison")
    - [How to Run ELK Stack on Docker](https://phoenixnap.com/kb/elk-stack-docker "Permalink to How to Run ELK Stack on Docker")
    
- Categories
    
- - [SysAdmin](https://phoenixnap.com/kb/category/sysadmin)
    - [Virtualization](https://phoenixnap.com/kb/category/virtualization)
    - [DevOps and Development](https://phoenixnap.com/kb/category/devops-and-development)
    - [Security](https://phoenixnap.com/kb/category/security)
    - [Backup and Recovery](https://phoenixnap.com/kb/category/backup-and-recovery)
    - [Bare Metal Servers](https://phoenixnap.com/kb/category/bare-metal-servers)
    - [Web Servers](https://phoenixnap.com/kb/category/web-servers)
    - [Networking](https://phoenixnap.com/kb/category/networking)
    - [Databases](https://phoenixnap.com/kb/category/databases)
    

- [COLOCATION](https://phoenixnap.com/colocation)
    
- - [Phoenix](https://phoenixnap.com/colocation/phoenix)
    - [Ashburn](https://phoenixnap.com/colocation/ashburn)
    - [Amsterdam](https://phoenixnap.com/colocation/amsterdam)
    - [Atlanta](https://phoenixnap.com/colocation/atlanta)
    - [Belgrade](https://phoenixnap.com/colocation/belgrade)
    - [Singapore](https://phoenixnap.com/colocation/singapore)
    
- [PROMOTIONS](https://phoenixnap.com/promotions)
    

- [SERVERS](https://phoenixnap.com/servers/dedicated)
    
- - [Dedicated Servers](https://phoenixnap.com/servers/dedicated)
    - [Database Servers](https://phoenixnap.com/servers/database)
    - [Virtualization Servers](https://phoenixnap.com/servers/virtualization)
    - [High Performance Computing (HPC) Servers](https://phoenixnap.com/servers/high-performance-computing-hpc)
    - [Dedicated Streaming Servers](https://phoenixnap.com/servers/streaming)
    - [Dedicated Game Servers](https://phoenixnap.com/servers/dedicated-game-servers)
    - [Dedicated Storage Servers](https://phoenixnap.com/servers/storage)
    - [SQL Server Hosting](https://phoenixnap.com/servers/sql-server-hosting)
    - [Dedicated Servers in Amsterdam](https://phoenixnap.com/dedicated-servers-amsterdam-netherlands)
    - [Cloud Servers in Europe](https://phoenixnap.com/cloud-services/cloud-servers-europe)
    - [Big Memory Infrastructure](https://phoenixnap.com/bare-metal-cloud/big-memory-infrastructure)
    
- [BUY NOW](https://admin.phoenixnap.com/wap-pncpadmin-shell/orderForm?bmbPath=/order-form?currencyCode=usd)
    

- CLOUD SERVICES
    
- - [Data Security Cloud](https://phoenixnap.com/security/data-security-cloud)
    - [VPDC](https://phoenixnap.com/cloud-services/virtual-private-data-center)
    - [Managed Private Cloud](https://phoenixnap.com/private)
    - [Object Storage](https://phoenixnap.com/object-storage)
    
- [SERVERS](https://phoenixnap.com/infrastructure-solutions)
    
- - [Disaster Recovery](https://phoenixnap.com/infrastructure-solutions/disaster-recovery-services)
    - [Web Hosting Reseller](https://phoenixnap.com/reseller-hosting)
    - [SaaS Hosting](https://phoenixnap.com/infrastructure-solutions/saas-hosting)
    

- INDUSTRIES
    
- - [Web Hosting Providers](https://phoenixnap.com/reseller-hosting)
    - [Legal](https://phoenixnap.com/infrastructure-solutions/legal-it)
    - [MSPs & VARs](https://phoenixnap.com/infrastructure-solutions/it-partners)
    - [Media Hosting](https://phoenixnap.com/infrastructure-solutions/media-hosting)
    - [Online Gaming](https://phoenixnap.com/infrastructure-solutions/online-gaming)
    - [SaaS Hosting Solutions](https://phoenixnap.com/infrastructure-solutions/saas-hosting)
    - [Ecommerce Hosting Solutions](https://phoenixnap.com/infrastructure-solutions/ecommerce-hosting)
    
- COMPLIANCE
    
- - [HIPAA Ready Hosting](https://phoenixnap.com/compliance/hipaa-compliant-hosting)
    - [PCI Compliant Hosting](https://phoenixnap.com/compliance/pci-compliant-hosting)
    
- NEEDS
    
- - [Disaster Recovery Solutions](https://phoenixnap.com/infrastructure-solutions/disaster-recovery-services)
    - [High Availability Solutions](https://phoenixnap.com/infrastructure-solutions/high-availability-solutions)
    - [Cloud Evaluation](https://phoenixnap.com/offers/cloud-evaluation-demo)
    

- COMPANY
    
- - [About Us](https://phoenixnap.com/company/about-us)
    - [GitHub](https://github.com/phoenixnap)
    - [Blog](https://phoenixnap.com/blog)
    - [RFP Template](https://phoenixnap.com/company/it-resources/data-center-rfp-template)
    - [Careers](http://employment.ccbill.com/)
    
- CONNECT
    
- - [Events](https://phoenixnap.com/company/it-events)
    - [Press](https://phoenixnap.com/company/press)
    - [Contact Us](https://phoenixnap.com/contact-us)
    

- [PhoenixNAP Home](https://phoenixnap.com/)
- [Blog](https://phoenixnap.com/blog)
- [Resources](https://phoenixnap.com/company/it-resources)
- [Glossary](https://phoenixnap.com/glossary)
- [GitHub](https://github.com/phoenixnap)
- [RFP Template](https://phoenixnap.com/company/it-resources/data-center-rfp-template)

- [Live Chat](https://phoenixnap.com/)
- [Get a Quote](https://phoenixnap.com/contact-us)
-  Support | [1-855-330-1509](tel:1-855-330-1509)
-  Sales | [1-877-588-5918](tel:1-877-588-5918)

- [Contact Us](https://phoenixnap.com/contact-us)
- [Legal](https://phoenixnap.com/cs/legal/)
- [Privacy Policy](https://phoenixnap.com/infrastructure-solutions/legal-it/privacy-shield-compliant-privacy-policy)
- [Terms of Use](https://phoenixnap.com/cs/legal/aup.html)
- [DMCA](https://phoenixnap.com/cs/legal/dmca.html)
- [GDPR](https://phoenixnap.com/gdpr)
- [Sitemap](https://phoenixnap.com/sitemap)

© 2022 Copyright phoenixNAP | Global IT Services. All Rights Reserved.