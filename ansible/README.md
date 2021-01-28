# Ansible (Automated CI/CD)

### Information

This Ansible tool works with Linux (Debian 8, 9, 10, Ubuntu 14.04 to 20.04, Mac OS with Homebrew cask and Windows 10)

### Installation

First, you need to install some tools into your machine to make work properly automated CI/CD : 

- [Ansible v2.9.x](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Packer v1.6.x](https://learn.hashicorp.com/tutorials/packer/getting-started-install)

If you have already a version of `virtualbox`, you have to be sure that version `6.1.16` or higher is installed or remove this before launch ansible tasks.

/!\ Warning - If you are on `MacOS`, you need to have to install : 

- [Homebrew](https://brew.sh/index_fr)

### Environment Variables

After, you must add some environement variables into `.env` file. You can check `.env.example` file to see all variables. But here, we listed all variables to add if you need more information : 

- `LOCAL_USERNAME` Username to your user in local machine.

### Ansible tasks

**LINUX**

- Update packages
- Install virtualbox
- Create and configure Debian vm into virtualbox
- Import vm into virtualbox

**Mac OS**

- Install community.general from Ansible Galaxy (to use homebrew)
- Install virtualbox
- Create and configure Debian vm into virtualbox
- Import vm into virtualbox

**Windows**

- Install ansible.windows from Ansible Galaxy
- Install virtualbox
- Create and configure Debian vm into virtualbox
- Import vm into virtualbox

### Launch Ansible tasks

To launch ansible tasks you must run this command line :

```
ansible-playbook -i hosts playbook.yml --ask-become-pass
```

### TroubleShooting

**VM Installation**

If you have troubleshooting to create and configure VM into virtualbox.
If you already have a VM with the same name of VM to create. For that, you can remove VM in Linux with this command line `rm -Rf /root/VirtualBox\ VMs/vm_name`. (change name with your VM name defined into variables `group_vars/all.yml`). And you can remove `output-virtualbox-nginx`, `output-virtualbox-db`, `output-virtualbox-back`, `output-virtualbox-front` folders.