#Oracle 12c Vagrant

Following these instructions will create a VirtualBox VM, Install Oracle 12cR1 software, Patch it, and then create a container database with one pluggable database.

## Prerequisites

### VirtualBox

http://virtualbox.com

### Packer

http://packer.io

### Vagrant

http://vagrantup.com

### Oracle Linux 6.5

1. Download Oracle Linux 6.5 DVD ISO
2. Rename and move it to packer/oracle_linux_6.5.iso

### Oracle 12cR1

1. Download Database Install files (1 and 2) - http://www.oracle.com/technetwork/database/enterprise-edition/downloads/database12c-linux-download-1959253.html
2. Place the zip archives in database_installer/


## Build Vagrant Box Image Using Packer

    $ cd {project root}
    $ cd packer
    $ ./buildbox.sh

## Import into Vagrant

    $ cd {project root}
    $ cd packer
    $ ./importbox.sh

## Run Vagrant Box

    $ cd {project root}
    $ vagrant up
    $ vagrant ssh

## Run Oracle 12c Installation Script

    [vagrant@vagrant-ol6 ~]$ sudo /vagrant/scripts/oracle12c-install.sh

## Connect to Database

  Default password for sys, system is vagrant - Port 1521 - service cdb12c

