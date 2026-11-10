*This project has been created as part of the 42 curriculum by gblas-he.*

# Born2beroot

## Description

Born2beroot is a system administration project from the 42 curriculum. The objective is to create and configure a secure Linux server inside a virtual machine while following a set of mandatory security and administration rules.

The project introduces fundamental concepts of Linux system administration, virtualization, user and group management, storage management, networking, firewalls, secure remote access and task automation.

The virtual machine was created using VirtualBox and Debian Stable without any graphical environment, following the project requirements.

---

# Project description

The server was configured according to the mandatory requirements.

The main design choices were:

- Debian Stable as the operating system.
- VirtualBox as the virtualization software.
- LVM for logical partition management.
- Encrypted partitions.
- SSH configured on port 4242.
- Root login disabled through SSH.
- UFW firewall allowing only port 4242.
- AppArmor enabled.
- Strong password policy using PAM.
- Secure sudo configuration.
- Bash monitoring script executed automatically every 10 minutes using cron.

---

# Technical choices

## Operating System

### Debian

Advantages

- Stable.
- Excellent documentation.
- Large community.
- Frequently used on servers.
- Easy package management with apt.

Disadvantages

- Packages are usually older than in rolling-release distributions.
- Less focused on enterprise support than Red Hat based systems.

---

### Why Debian?

Debian was chosen because it is stable, beginner-friendly for system administration, has excellent documentation and is officially recommended for newcomers in the project subject.

---

# Partitioning

The virtual machine uses LVM (Logical Volume Manager).

Advantages:

- Logical volumes can be resized easily.
- Better storage flexibility.
- Easier disk administration.
- Better scalability.

Encrypted partitions protect stored information if the virtual disk is accessed without authorization.

---

# Security

The server was configured with:

- SSH running on port 4242.
- Root login disabled.
- UFW firewall enabled.
- Only TCP port 4242 allowed.
- Strong password policy.
- Secure sudo configuration.
- AppArmor enabled.

---

# Monitoring

A Bash script called **monitoring.sh** displays:

- Operating system architecture.
- Physical CPUs.
- Virtual CPUs.
- RAM usage.
- Disk usage.
- CPU usage.
- Last reboot.
- LVM status.
- Active TCP connections.
- Logged users.
- IP address.
- MAC address.
- Number of sudo commands executed.

The script is automatically executed every 10 minutes using cron.

---

# Debian vs Rocky Linux

| Debian | Rocky Linux |
|---------|-------------|
| Community maintained | Enterprise oriented |
| Uses .deb packages | Uses .rpm packages |
| Uses apt | Uses dnf |
| Easier for beginners | Common in enterprise environments |
| Excellent documentation | Compatible with Red Hat Enterprise Linux |

---

# AppArmor vs SELinux

## AppArmor

Advantages

- Easier configuration.
- Profile-based.
- Simpler to learn.
- Default security framework in Debian.

Disadvantages

- Less granular than SELinux.

---

## SELinux

Advantages

- Very powerful.
- Fine-grained access control.
- Standard in Red Hat based systems.

Disadvantages

- More complex configuration.
- Harder for beginners.

---

# UFW vs firewalld

## UFW

Advantages

- Very easy to configure.
- User-friendly.
- Ideal for Debian.

Disadvantages

- Fewer advanced features.

---

## firewalld

Advantages

- Dynamic rule management.
- Zones support.
- Enterprise oriented.

Disadvantages

- More complex.

---

# VirtualBox vs UTM

## VirtualBox

Advantages

- Cross-platform.
- Free.
- Mature software.
- Excellent documentation.

Disadvantages

- Lower performance than native execution.

---

## UTM

Advantages

- Native support for Apple Silicon.
- Uses QEMU.
- Better integration on Apple Silicon.

Disadvantages

- Less common outside macOS.

---

# Instructions

## Requirements

- VirtualBox
- Debian Stable ISO

## Installation

1. Create a new virtual machine.
2. Install Debian Stable.
3. Configure encrypted LVM partitions.
4. Install sudo and SSH.
5. Configure UFW.
6. Configure AppArmor.
7. Configure the password policy.
8. Configure sudo.
9. Create monitoring.sh.
10. Configure cron.

---

# Resources

## Official documentation

- Debian Documentation
- VirtualBox Documentation
- OpenSSH Documentation
- UFW Documentation
- AppArmor Documentation
- PAM Documentation
- cron manual pages

## AI usage

AI tools were used minimally and exclusively for simple, repetitive tasks such as formatting markdown tables and proofreading documentation. All system installation, partitioning, security policies, service configurations, and scripting were performed manually.