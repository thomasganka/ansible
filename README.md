# Streamsets Ansible Playbooks

This project automates the configuration of Streamsets applications (and applications interacting with Streamsets) via Ansible. It also allows you to leverage Vagrant and Virtualbox to test out on your local machine before deploying to the Cloud or On-Premise infrastructure.

## Quick Start Guide

### 1 - Install dependencies (VirtualBox, Vagrant, Ansible)

  1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
  2. Download and install [Vagrant](http://www.vagrantup.com/downloads.html).
  3. [Mac/Linux only] Install [Ansible](http://docs.ansible.com/intro_installation.html).

Note for Windows users: *This guide assumes you're on a Mac or Linux host. Windows hosts are unsupported at this time.*

### 2 - Build the Virtual Machine (Testing with Vagrant)

  1. Download this project and put it wherever you want.
  2. Open Terminal, cd to this directory.
  4. Type in `vagrant up`, and let Vagrant do its magic.

Note: *If there are any errors during the course of running `vagrant up`, and it drops you back to your command prompt, just run `vagrant provision` to continue building the VM from where you left off. If there are still errors after doing this a few times, post an issue to this project's issue queue on GitHub with the error.*

### 3 - Edit Files

  1. Open Terminal, cd to application of choice (sdc, transformer, etc.)
  2. Edit the inventory file with: 
    a. an IP of the machine you want to configure (Public IP if it is a cloud provider machine)
    b. `ansible_ssh_private_key_file`, This is the location on the location machine of your ssh private key to access the machine to configure
    c. `ansible_ssh_user`, This is the ssh user of the machine you are to configure
  3. cd to provisioning
  4. Edit the vars.yml
    a. update the versions if needed
 
 
 ### 4 - Run the playbook: 
 
 Example: ```ansible-playbook -i inventory provisioning/playbook.yml```

## Additional Notes

  - To shut down the virtual machine, enter `vagrant halt` in the Terminal in the same folder that has the `Vagrantfile`. To destroy it completely (if you want to save a little disk space, or want to rebuild it from scratch with `vagrant up` again), type in `vagrant destroy`.
  
  - Currently the playbooks only support EL7, but support for other Linux OSes should be soon

## About the Author

This project was created by [Thomas Ganka](https://www.github.com/thomasganka) as an example for Ansible for Streamsets.
