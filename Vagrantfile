#Vagrantfile 
# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  config.ssh.insert_key = false
  (0..2).each do |i|	
    config.vm.define "apache-kafka-#{i}" do |node|
       node.vm.box = "ubuntu/xenial64"
       node.vm.host_name = "apache-kafka-#{i}"
       node.vm.network "private_network", ip: "192.168.2.1#{i}"
       node.vm.provider "virtualbox" do |vb|
         vb.cpus = 1
         vb.memory = "512"
       end
#       node.vm.provision "ansible" do |ansible|
#         ansible.verbose = "v"
#         ansible.playbook = "ansible/playbook-zookeeper-single.yml"
#	 ansible.inventory_path = "ansible/inventory/hosts_vagrant"
#       end
     end
  end
end
