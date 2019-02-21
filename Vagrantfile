Vagrant.configure("2") do |config|

  config.vm.define :DataBase do |db_config|
    db_config.vm.box = "centos_7"
    db_config.vm.hostname = "db" 
    db_config.vm.network :private_network, ip: "10.0.15.25"
    db_config.vm.network "forwarded_port", guest: 80, host: 8080
    db_config.vm.provider "virtualbox" do |vb|
      vb.memory = "256"
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "configdb.yaml"
  end

end
