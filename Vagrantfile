IMAGE_NAME = "bento/ubuntu-24.04"

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end

    config.vm.define "ubuntu" do |ubuntu|
        ubuntu.vm.box = IMAGE_NAME

        # SSH
        ubuntu.vm.network "forwarded_port", guest: 22, host: 2226, host_ip: "127.0.0.1"

        # HTTP (web)
        ubuntu.vm.network "forwarded_port", guest: 80, host: 8088, host_ip: "127.0.0.1"

        ubuntu.vm.hostname = "ubuntu"
    end

end
