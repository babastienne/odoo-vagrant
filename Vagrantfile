# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :odoo do |odoo|
    odoo.vm.box = "ubuntu/trusty64"
    odoo.vm.provision :shell, path: "setup_odoo.sh"
    odoo.vm.synced_folder "D:/e-cosi/perso/Documents/ECosi/WIP/addons", "/home/vagrant/SharedFolder"

    # Allow insecure box fetching
    odoo.vm.box_download_insecure = true

    odoo.vm.network "private_network", ip: "192.168.50.4"
    odoo.vm.hostname = "odoo"

    # Kill Odoo server instance launched by default each time the VM is booted
    odoo.vm.provision "shell", run: "always", inline: "kill `ps aux | awk '/odoo-bin/ {print $2}' | head -n1`"

    odoo.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    end
  end

end
