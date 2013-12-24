# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

$script = <<SCRIPT
  git --version
  echo node version `node --version`
  echo npm version `npm --version`
  sudo npm install --global --quiet bem-cli
  cd /vagrant
  git clone https://github.com/bem/project-stub.git
  cd project-stub
  npm config set bin-links false
  npm install --quiet
  echo "cd /vagrant/project-stub" >> /home/vagrant/.bashrc
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  config.vm.network :forwarded_port, guest: 8080, host: 3000

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "256", "--cpus",   "1"]
  end

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = :debug
    chef.add_recipe "git"
    chef.add_recipe "nodejs"
    chef.json = {
      "nodejs" => {
        "version" => "0.10.20"
	      #, "from_source" => true
      }
    }
  end
  config.vm.provision :shell, :inline => $script
end