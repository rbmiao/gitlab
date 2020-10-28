# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.hostname = "gitlab.local.dev"

    config.vm.network :private_network, ip: "172.34.56.78"
    config.vm.network :forwarded_port, guest: 80, host: 8080

    config.vm.provider "virtualbox" do |vb|
        vb.name = "GitLab Server"
        vb.memory = "4096"
        vb.cpus = "4"
    end

    config.vm.provision :docker
    config.vm.provision "shell", path: "install_gitlab.sh"
end

