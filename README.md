# Ansible lessen

This vagrant will install 3 Linux Ubuntu machines, 3x Linux servers.
It will add some default users, groups and directory's. User student will be added to the sudo group.
This Vagrant is to practice with Ansible and Linux server.
This repository is intended for educational purpose only.


## Prerequisites

Works on Windows 10 and tested on macOS (macOS needs the Virtualbox extension pack).

Software needed:
* Virtualbox 5.0 or higher
* Git bash for Windows
* Vagrant 2.2.6 or higher


## Demo installation && use Vagrant

Youtube: https://youtu.be/KABnIuaA8SM


## Installation

* Install Virtualbox: https://www.virtualbox.org/wiki/Downloads
* Install Git bash for Windows: https://gitforwindows.org/
* Install Vagrant for Windows: https://www.vagrantup.com/downloads.html

## Run this Vagrant VM
Open **Git Bash** in Windows
```
cd Documents
mkdir vagrant && cd vagrant
git clone https://github.com/borahuho/Ansible-lessen
cd Ansible-lessen
vagrant up
vagrant ssh server1
```
## Mission

Read the lessons on the Wikiwijs.

## Network
Vagrant VM will be set up with 2 network adapters
```
Nat : DHCP
Localhost (server1): 10.13.37.10

Nat : DHCP
Localhost (server2): 10.13.37.11

Nat : DHCP
Localhost (server3): 10.13.37.12
```
## Vagrant commands
Start VM's with Vagrant
```
vagrant up
```
Pause a VM
```
vagrant suspend
```
Restart a paused VM
```
vagrant resume
```
Stop and shutdown a VM
```
vagrant halt
```
Remove a VM
```
vagrant destroy
```
ssh in to the VM
```
vagrant ssh server1
vagrant ssh server2
vagrant ssh server3
```

