VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider :virtualbox do |config|
#   config.customize ["modifyvm", :id, "--memory", 1024]
  end
  config.vm.network "public_network", bridge: "eth0", ip: "192.168.1.50"
  config.vm.provision "shell", :inline => "sudo apt-get update && apt-get upgrade --force-yes"
  config.vm.provision "ansible" do |ansible|
          ansible.playbook = "playbook.yml"
  end
end
