# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
Vagrant.require_version ">= 1.5.0"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "precise64"
    config.vm.box_url = "http://files.vagrantup.com/precise64.box"

    config.vm.network :private_network, ip: "192.168.111.111"

    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
    end

    # This was causing sporadic vboxsf errors on some hosts with various
    # versions of VirtualBox and extensions on the guest. We'll just use
    # SFTP and avoid this nuisance.
    config.vm.synced_folder ".", "/vagrant", :disabled => true

    config.vm.provision "ansible" do |ansible|
        #ansible.verbose = "vvvv"
        ansible.playbook = "basic_btmux.yml"
        ansible.host_key_checking = false
        ansible.groups = {
          "developer" => ["default"],
        }
    end
end
