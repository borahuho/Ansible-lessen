$useraddscript = <<SCRIPT
useradd -s /bin/bash -c "Ansible testuser" -m student
echo 'student:Welcome01' | chpasswd
groupadd operators
usermod -aG operators student
usermod -aG sudo student
mkdir /operators
chown student /operators
chgrp operators /operators
SCRIPT


Vagrant.configure('2') do |config|
    
    # set default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
        vb.cpus = 1
    end

    config.vm.define "server1", primary: true do |machine1|
        machine1.vm.host_name = "server1.local"
        machine1.vm.network "private_network", ip: "10.13.37.10"
        machine1.vm.provision "shell", inline: $useraddscript
		machine1.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
        machine1.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
    end

    config.vm.define "server2", primary: false do |machine2|
        machine2.vm.host_name = "server2.local"
        machine2.vm.network "private_network", ip: "10.13.37.11"
        machine2.vm.provision "shell", inline: $useraddscript
		machine2.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
        machine2.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
    end

    config.vm.define "server3", primary: false do |machine3|
        machine3.vm.host_name = "server3.local"
        machine3.vm.network "private_network", ip: "10.13.37.12"
        machine3.vm.provision "shell", inline: $useraddscript
		machine3.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
        machine3.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
        end
    end
end