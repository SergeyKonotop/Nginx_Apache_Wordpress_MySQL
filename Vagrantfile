# -*- mode: ruby -*-
# vi: set ft=ruby :

###################################################################################################

Vagrant.configure("2") do |config|

 config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
    v.customize ["modifyvm", :id, "--memory", "512", "--cpus", "1"]
  end

 config.vm.define "ansible" do |serv|
    serv.vm.box = "ubuntu/xenial64"
    serv.vm.hostname = "ansible"
    serv.vm.network :private_network, ip: "192.168.56.110"
#    netmask: "27",
#    virtualbox__intnet: true
#    serv.vm.network :private_network, type: "dhcp"
    serv.vm.provider "virtualbox" do |pmv|
      pmv.memory = 1024
      pmv.cpus = 1
	end
#   git install
	serv.vm.provision "shell", inline: "sudo apt-get install git -y"
#   ansible install
#	serv.vm.provision "shell", inline: "sudo apt-get install software-properties-common"
#	serv.vm.provision "shell", inline: "sudo apt-add-repository ppa:ansible/ansible -y"
#	serv.vm.provision "shell", inline: "sudo apt-get update -y"
#	serv.vm.provision "shell", inline: "sudo apt-get install ansible -y"
	serv.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user.yml"
	end  
#   pip install
    serv.vm.provision "shell", inline: "sudo apt-get install python-pip -y"
	serv.vm.provision "file", source: "ansible_key", destination: "/tmp"
	serv.vm.provision "shell", inline: "sudo cp /tmp/hosts /etc/ansible"
	serv.vm.provision "shell", inline: "sudo cp /tmp/ansible.cfg /etc/ansible"
	serv.vm.provision "shell", inline: "sudo cp /tmp/ansible /home/ansible/.ssh"
	serv.vm.provision "shell", inline: "sudo cp -r /tmp/roles /home/ansible"
	serv.vm.provision "shell", inline: "sudo cp /tmp/*.yml /home/ansible"
	serv.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end

 config.vm.define "fe-stag" do |c1|
    c1.vm.box = "ubuntu/xenial64"
    c1.vm.hostname = "fe-stag"
    c1.vm.network :private_network, ip: "192.168.56.111"
#	netmask: "27",
#   virtualbox__intnet: true
#	c1.vm.network :private_network, type: "dhcp"
#   python install
	c1.vm.provision "shell", inline: "sudo apt-get update -y"
	c1.vm.provision "shell", inline: "sudo apt-get install python -y"
	c1.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c1.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c1.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end

 config.vm.define "be1-stag" do |c2|
    c2.vm.box = "ubuntu/xenial64"
    c2.vm.hostname = "be1-stag"
    c2.vm.network :private_network, ip: "192.168.56.112"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c2.vm.network :private_network, type: "dhcp" 
#   python install
	c2.vm.provision "shell", inline: "sudo apt-get update -y"
	c2.vm.provision "shell", inline: "sudo apt-get install python -y"
	c2.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c2.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c2.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
 config.vm.define "be2-stag" do |c3|
    c3.vm.box = "ubuntu/xenial64"
#	c3.vm.box = "apnunes/xenial-python"
    c3.vm.hostname = "be2-stag"
    c3.vm.network :private_network, ip: "192.168.56.113"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c3.vm.network :private_network, type: "dhcp" 
#   python install
	c3.vm.provision "shell", inline: "sudo apt-get update -y"
	c3.vm.provision "shell", inline: "sudo apt-get install python -y"
	c3.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c3.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c3.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
 config.vm.define "db1-stag" do |c4|
    c4.vm.box = "ubuntu/xenial64"
    c4.vm.hostname = "db1-stag"
    c4.vm.network :private_network, ip: "192.168.56.114"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c4.vm.network :private_network, type: "dhcp" 
#   python install
	c4.vm.provision "shell", inline: "sudo apt-get update -y"
	c4.vm.provision "shell", inline: "sudo apt-get install python -y"
	c4.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c4.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c4.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
 config.vm.define "db2-stag" do |c5|
    c5.vm.box = "ubuntu/xenial64"
#	c5.vm.box = "apnunes/xenial-python"
    c5.vm.hostname = "db2-stag"
    c5.vm.network :private_network, ip: "192.168.56.115"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c5.vm.network :private_network, type: "dhcp" 
#   python install
	c5.vm.provision "shell", inline: "sudo apt-get update -y"
	c5.vm.provision "shell", inline: "sudo apt-get install python -y"
	c5.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c5.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c5.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
 config.vm.define "fe-prod" do |c6|
    c6.vm.box = "ubuntu/xenial64"
    c6.vm.hostname = "fe-prod"
    c6.vm.network :private_network, ip: "192.168.56.116"
#	netmask: "27",
#	virtualbox__intnet: true
#	c6.vm.network :private_network, type: "dhcp"
#   python install
	c6.vm.provision "shell", inline: "sudo apt-get update -y"
	c6.vm.provision "shell", inline: "sudo apt-get install python -y"
	c6.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c6.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c6.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end

 config.vm.define "be1-prod" do |c7|
    c7.vm.box = "ubuntu/xenial64"
    c7.vm.hostname = "be1-prod"
    c7.vm.network :private_network, ip: "192.168.56.117"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c7.vm.network :private_network, type: "dhcp" 
#   python install
	c7.vm.provision "shell", inline: "sudo apt-get update -y"
	c7.vm.provision "shell", inline: "sudo apt-get install python -y"
	c7.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c7.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c7.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
  config.vm.define "be2-prod" do |c8|
    c8.vm.box = "ubuntu/xenial64"
    c8.vm.hostname = "be2-prod"
    c8.vm.network :private_network, ip: "192.168.56.118"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c8.vm.network :private_network, type: "dhcp" 
#   python install
	c8.vm.provision "shell", inline: "sudo apt-get update -y"
	c8.vm.provision "shell", inline: "sudo apt-get install python -y"
	c8.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c8.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c8.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
  config.vm.define "db1-prod" do |c9|
    c9.vm.box = "ubuntu/xenial64"
    c9.vm.hostname = "db1-prod"
    c9.vm.network :private_network, ip: "192.168.56.119"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c9.vm.network :private_network, type: "dhcp" 
#   python install
	c9.vm.provision "shell", inline: "sudo apt-get update -y"
	c9.vm.provision "shell", inline: "sudo apt-get install python -y"
	c9.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c9.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c9.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
 
  config.vm.define "db2-prod" do |c10|
    c10.vm.box = "ubuntu/xenial64"
#	c10.vm.box = "apnunes/xenial-python"
    c10.vm.hostname = "db2-prod"
    c10.vm.network :private_network, ip: "192.168.56.120"
#    netmask: "27",	
#	virtualbox__intnet: true
#	c10.vm.network :private_network, type: "dhcp" 
#   python install
	c10.vm.provision "shell", inline: "sudo apt-get update -y"
	c10.vm.provision "shell", inline: "sudo apt-get install python -y"
	c10.vm.provision "file", source: "ansible_key_pub", destination: "/tmp"
    # Run Ansible from the Vagrant VM 
    c10.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "user_key.yml"
	end
	c10.vm.provision "shell", inline: "sudo cp /tmp/sudoers /etc"
 end
end