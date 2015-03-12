# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # PuppetMaster
  config.vm.define "puppetmaster", primary: true do |puppet|
    puppet.vm.box = "puppetmaster"
    puppet.vm.hostname = "puppet.example.com"
    puppet.vm.network :forwarded_port, guest: 8140, host: 8141, id: "puppet"
    puppet.vm.network :private_network, ip: "192.168.50.100"
    puppet.vm.network :forwarded_port, guest: 22, host: 2222, id: "ssh"
  end

  # Example Node (cascadia)
  config.vm.define "cascadia" do |casit|
    casit.vm.box = "cascadia"
    casit.vm.hostname = "cascadia.example.com"
    casit.vm.network :private_network, type: "dhcp"
    casit.vm.network :forwarded_port, guest: 22, host: 2223, id: "ssh"
  end

end
