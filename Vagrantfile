# -*- mode: ruby -*-
# vi: set ft=ruby :
#
ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
    config.vm.define :guest do |guest_config|
            guest_config.vm.box = "ubuntu/trusty64"
            guest_config.ssh.forward_agent = true
             
            #HostManager Start

            guest_config.hostmanager.enabled = true
            guest_config.hostmanager.manage_host = false
            guest_config.hostmanager.ignore_private_ip = true
            guest_config.hostmanager.include_offline = true

            #HostManager Finish
            # This will give the machine a static IP uncomment to enable
            guest_config.vm.network :private_network, ip: "192.168.20.10"
            #virtualbox__intnet: true
            guest_config.vm.network "public_network"
            guest_config.vm.network :forwarded_port, guest: 80, host: 8888, auto_correct: true
            #guest_config.vm.network :forwarded_port, guest: 3306, host: 8889, auto_correct: true
            #guest_config.vm.network :forwarded_port, guest: 5432, host: 5433, auto_correct: true
            #guest_config.vm.network :forwarded_port, guest: 27017, host: 8887, auto_correct: true
            #guest_config.vm.network :forwarded_port, guest: 8080, host: 8881, auto_correct: true

            guest_config.vm.hostname = "ubuntu.app"

            guest_config.vm.synced_folder "./","/var/www/project", {:mount_options => ['dmode=777','fmode=777']}

            guest_config.vm.provider :virtualbox do |v|
                v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
                v.customize ["modifyvm", :id, "--memory", "512"]
            end

            guest_config.vm.provision "ansible" do |ansible|
                ansible.playbook = "provision/playbook.yml"
                ansible.inventory_path = "provision/inventory"
                ansible.limit = "all"
                ansible.sudo = true
            end
           
    end
end
