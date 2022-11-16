
# VM Info
VM_BOX = "generic/ubuntu2004"
HOST_NAME = "ubuntu-host"
HOST_CPUS = 1
HOST_MEMORY = 1024
HOST_IP = "192.168.56.5"
HOST_PORT = 2200



Vagrant.configure("2") do |config|

    # VM images
    config.vm.box = VM_BOX

    # Check update off
    config.vm.box_check_update = false

    # Define VM
    config.vm.define "ubuntu" do |subConfig|

        # Setup vm provider (virtualbox)
        subConfig.vm.provider "virtualbox" do |vm|
            # Virtual box name
            vm.name = 'ubuntu-box'

            vm.cpus = HOST_CPUS
            vm.memory = HOST_MEMORY
        end

        # Setup the hostname
        subConfig.vm.hostname = HOST_NAME

        
        # Setup Network
        subConfig.vm.network "forwarded_port", guest: 22, host: "#{HOST_PORT}"
        subConfig.vm.network :private_network, ip: HOST_IP

    end
end