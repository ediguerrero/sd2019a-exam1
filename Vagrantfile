Vagrant.configure("2") do |config|


  # create load balancer

  config.vm.define :lb do |lb_config|
      lb_config.vm.box = "centos_7"
      lb_config.vm.hostname = "lb"
      lb_config.vm.network :private_network, ip: "10.0.15.25"
      lb_config.vm.network "forwarded_port", guest: 80, host: 8080
      lb_config.vm.provider "virtualbox" do |vb|
        vb.memory = "256"
      end
config.vm.define "database" do |db|
  db.vm.box = "centos_7"
  db.vm.hostname = "database"
  db.vm.network "private_network", ip: "10.0.15.25"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "MySQLInstall.yml"
  end



#lb_config.vm.provision "shell",path: "keys.sh"

end
end
