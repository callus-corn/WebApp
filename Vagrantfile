VARGRANTFILE_API_VERSION = "2"

Vagrant.configure(VARGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"

  config.vm.define "web" do | web |
  	web.vm.hostname = "web"
  	web.vm.network "private_network", ip: "192.168.33.10", virtualbox__intent: "intent"

  	web.vm.provision :ansible_local do | ansible |
  		ansible.limit = "web"
  		ansible.playbook = "provision/site.yml"
  		ansible.inventory_path = "provision/development"
  	end

  end

  config.vm.define "app" do | app |
  	app.vm.hostname = "app"
  	app.vm.network "private_network", ip: "192.168.33.20", virtualbox__intent: "intent"

  	app.vm.provision :ansible_local do | ansible |
  		ansible.limit = "app"
  		ansible.playbook = "provision/site.yml"
  		ansible.inventory_path = "provision/development"
  	end

  end

  config.vm.define "db" do | db |
  	db.vm.hostname = "db"
  	db.vm.network "private_network", ip: "192.168.33.30", virtualbox__intent: "intent"

  	db.vm.provision :ansible_local do | ansible |
  		ansible.limit = "db"
  		ansible.playbook = "provision/site.yml"
  		ansible.inventory_path = "provision/development"
  	end

  end

  config.vm.define "front" do | front |
    front.vm.hostname = "front"
    front.vm.network "private_network", ip: "192.168.33.40", virtualbox__intent: "intent"

    front.vm.provision :ansible_local do | ansible |
      ansible.limit = "front"
      ansible.playbook = "provision/site.yml"
      ansible.inventory_path = "provision/development"
    end

  end

end
