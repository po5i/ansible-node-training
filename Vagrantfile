# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/centos7"
  # config.vm.network :private_network, ip: "192.168.55.55"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 256
    v.linked_clone = true
  end

  # App server
  config.vm.define "webserver" do |app|
    app.vm.hostname = "nodejs.test"
    app.vm.network :forwarded_port, guest: 80, host: 3000
    app.vm.network "public_network"
  end
end