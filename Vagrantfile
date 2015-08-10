# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.define 'docker' do |machine|
    machine.vm.hostname = 'echaloasuerte1'
    machine.vm.network "private_network", ip: "192.168.77.23"

    machine.vm.provision :ansible do |ansible|
      ansible.playbook = "main.yml"
      ansible.sudo = true
      ansible.verbose = 'vvvv'

      # Disable default limit (required with Vagrant 1.5+)
      ansible.limit = 'all'

    end
  end

end
