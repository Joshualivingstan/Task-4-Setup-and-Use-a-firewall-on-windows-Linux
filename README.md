
# Task-4-Setup-and-use-a-Firewall-on-Windows-Linux

## Tasks
In kali linux terminal

## Introduction
In this project,  A firewall is a network security device either hardware or software-based which monitors all incoming and outgoing traffic and based on a defined set of security rules it accepts, rejects, or drops that specific traffic. It acts like a security guard that helps keep your digital world safe from unwanted visitors and potential threats.

**Types of rules in Firewall:**

  1.Accept: allow the traffic.
  2.Reject: block the traffic but reply with an “unreachable error”.
  3.Drop: block the traffic with no reply.
## Pre-requisites
- Basic understanding of networking.  
- The ability to define network zones and IP addresses.
- Knowledge of common firewall services and logging.

## Lab Set-up and Tools

### Tools
- **Kali Linux:** Use UFW(Uncomplicated Firewall) an open configuration tool on linux .
- **UFW(Uncomplicated Firewall):** UFW (Uncomplicated Firewall) is a command-line tool that simplifies firewall configuration on Ubuntu and Debian-based systems. It provides a user-friendly interface for managing iptables rules, the Linux kernel's packet filtering system.
                                                       **or**
- **Windows Firewall**:Windows Firewall is a built-in network security feature that protects your device by controlling and monitoring network traffic.

### Installation
Install UFW(Uncomplicated Firewall) on a linux system using the command :
```sh
sudo apt update && sudo apt install ufw
```
<img width="959" alt="image" src="https://github.com/user-attachments/assets/65f994bb-3e0c-43ba-b772-d7e1fac987f6" />

## Tasks
In kali linux terminal
# Setup and use a Firewall .
**Objective:** Configure and test the basic firewall rules to allow or block traffic.
**Tools:** Windows firewall / UFW(Uncomplicated firewall)on linux.
## 1. Enable UFW
Before starting, install and update UFW.To enable UFWuse the command:

 ```sh
sudo ufw enable
```
<img width="958" alt="image" src="https://github.com/user-attachments/assets/af159bc7-fd23-4ef1-a838-c070bbedccf5" />



## 2.List current firewall rules

**Use command:**
 ```sh
sudo ufw status numbered
```
<img width="958" alt="image" src="https://github.com/user-attachments/assets/ab4810ff-5876-4ac6-aaca-f25359b3b741" />


## 3.Add a rule to block inbound traffic on a specific port(e.g., 23 for Telnet)
Block portal 23(Telnet) :
 ```sh
sudo ufw deny 23/tcp
```
**Rule added**

<img width="596" alt="image" src="https://github.com/user-attachments/assets/6260f1d3-db9d-4bae-a918-a8edbf647d5d" />

## 4.Test the rule
**Try the following commands and it should fail**
 ```sh
telnet localhost 23
```
                        (or)
 ```sh
nc -zv localhost 23
```
<img width="794" alt="image" src="https://github.com/user-attachments/assets/abd55dba-7a5c-4b92-9628-e1fe3291b18a" />


## 5.Add rule to allow SSH(port 22)
**Use command:**
 ```sh
sudo ufw allow 22/tcp
```
**Rule added to allow the port**
<img width="410" alt="image" src="https://github.com/user-attachments/assets/469b6ef6-0d67-4cb4-845d-6066dfdcf6cb" />


## 6.Remove the test block rule
**To restore the original state by using the command:**
 ```sh
sudo ufw delete deny 23/tcp
```
**Rule will be deleted and restores to allow 23/tcp**
<img width="479" alt="image" src="https://github.com/user-attachments/assets/6a5569d2-457e-4f48-9d82-871657645d16" />

## 7.Final status
**Shows the status of firewall after performing the rules**
<img width="893" alt="image" src="https://github.com/user-attachments/assets/17fedbed-84f5-4b29-bdd2-98ca913a8560" />

## 8.Firewall Summary

🧠 Firewall Summary

*A firewall filters incoming and outgoing network traffic based on a set of rules.

*It can block/allow traffic based on IP addresses, port numbers, or protocols.

*Example: Blocking port 23 prevents Telnet connections, which reduces exposure to certain attacks.

*Allowing only essential services, like SSH, reduces the attack surface.
