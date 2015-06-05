# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.7.2"

Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.ssh.insert_key = true
  config.vm.box = "parallels/centos-7.0"
  config.vm.define "rea"

  config.vm.hostname = 'rea.local'
  config.vm.network "private_network", ip: "192.168.13.37"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/ansible/site.yml"
    ansible.extra_vars = { ansible_ssh_user: "vagrant" }
    # ansible.verbose = "vvvv"
  end
end
