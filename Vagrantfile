Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

  config.vm.define "kubernetes_master" do |m|
    m.vm.network "private_network", ip: "192.168.50.115", bridge: "wlp3s0"
    m.vm.network "forwarded_port", guest: 6443, host: 6443
  end

  config.vm.define "kubernetes_slave" do |s|
    s.vm.network "private_network", ip: "192.168.50.116", bridge: "wlp3s0"
  end
end
