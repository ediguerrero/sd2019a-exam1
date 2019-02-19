
Vagrant.configure("2") do |config|
config.vm.define "web1" do |node|
        node.vm.box = "centos_7"
        node.vm.hostname = "web1"
        node.vm.network :private_network, ip: "10.0.15.21"
        node.vm.network "forwarded_port", guest: 80, host: "8081"
end
config.vm.define "web2" do |node|
        node.vm.box = "centos_7"
        node.vm.hostname = "web2"
        node.vm.network :private_network, ip: "10.0.15.22"
        node.vm.network "forwarded_port", guest: 80, host: "8082"
end
config.vm.define "load_balancer" do |lb_config|
        lb_config.vm.box = "centos_7"
        lb_config.vm.hostname = "lb"
        lb_config.vm.network :private_network, ip: "10.0.15.11"
        lb_config.vm.network "forwarded_port", guest: 80, host: 8011

end
end
