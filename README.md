# Rails/Ember Application Server

This server architecture is built with Vagrant with Ansible provisioning. Stack is as follows:

* CentOS 7
* Non-global Ruby/Node
* Nginx/Unicorn via Unix socket

### Development Requirements

* [Homebrew](http://brew.sh) - System package manager
* [Ansible](http://docs.ansible.com/intro_installation.html) - SSH based provisioner. `brew install ansible`
* [Vagrant](https://www.vagrantup.com/downloads.html) - Script VMs

### Usage

* Edit ./provisioning/ansible/default.yml file.
* Copy local users' public ssh key to `./provisioning/ansible/roles/app/files/public_keys/`
* `vagrant up`, or provision to live via hosts file and ansible
* Edit mina config file - `config/deploy.rb` in Rails project
* Make sure the git repository for the project is accessible via the server. (Example: If it's
  a private repository on GitHub, please setup a deploy user with a read-only access.)
* From your Rails project, do `mina setup` and `mina deploy`
