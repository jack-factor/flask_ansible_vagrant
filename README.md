VAGRANT UBUNTU 16.04 - NGINX GUNICORN MYSQL FLASK
=================================================

Description:
-----------

Virtualbox and vagrant used to build virtual machines as servers.  
This vagrant profile install Nginx, Mysql, Python3, Flask.  
I use the lastest [Ubuntu 16.04 x64](https://atlas.hashicorp.com/ubuntu/boxes/trusty64/) image  

Prerequisites / Requirements
----------------------------
install these requirements

1. Download and Install [VitualBox](https://www.virtualbox.org/wiki/Downloads)
2. Download and Install [Vagrant](https://www.vagrantup.com/downloads.html)
3. Install [guest additions to Vagrant](https://github.com/dotless-de/vagrant-vbguest)  
 `vagrant plugin install vagrant-vbguest`
4. Install [vagrant hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager)  
 `vagrant plugin install vagrant-hostmanager`
5. Install [Ansible](http://docs.ansible.com/ansible/intro_installation.html).  
  `sudo pip install ansible`
5. Install [Git](https://git-scm.com/).  

Getting Started
---------------
1. clone this repository:
  `git clone git@github.com:jack-factor/flask_ansible_vagrant.git`
2. Modify /etc/hosts file. Add this line:  
  `192.168.20.10 project.app`
3. Start Vagrant VM:
  `vagrant up`
4. Open your browser:
  `http://project.app`


> Note:  
   * If something goes wrong. You can re-provision Vagrant VM  
    `vagrant provision`
   * If you want to delete the Vagrant VM  
    `vagrant destroy`
   * You can shut down the Vagrant VM  
    `vagrant destroy`
