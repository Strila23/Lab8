ENV["VAGRANT_EXPERIMENTAL"] = "disks"

Vagrant.configure("2") do |config|

    config.vm.define "rrmmeight" do |rrmmeight|

        rrmmeight.vm.hostname = "rrmmeight"
        rrmmeight.vm.box = "centos/7"
        rrmmeight.vm.network "private_network", ip: "192.168.33.10"

        config.vm.network "forwarded_port", guest: 443, host: 8443, host_ip: "127.0.0.1"
        config.vm.network "forwarded_port", guest: 80, host: 8888, host_ip: "127.0.0.1"

        rrmmeight.vm.provider "virtualbox" do |vb|
            vb.name = "rrmmeight"
            vb.gui = false
            vb.memory = "1024"
        end

        config.vm.provision "shell", run: "always", path: "script.sh"
    end
end
