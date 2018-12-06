Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.define "giropops" do |cf|
    config.vm.hostname = "giropops-vagrantbox"
  	cf.vm.box = "ubuntu/bionic64"
  	cf.vm.network "private_network", ip: "192.168.50.10"
  	cf.vm.provision "ansible" do |ansible|
      ansible.verbose = true
    	ansible.playbook = "ansible/provisioning.yml"
      ansible.raw_arguments = ["-e", "ansible_python_interpreter=/usr/bin/python3"]
  	end
  end
end
