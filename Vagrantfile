Vagrant.configure("2") do |config|
  #config.vm.box = "ubuntu-64-chef-11"
  #config.vm.box_url = "http://grahamc.com/vagrant/ubuntu-12.04-omnibus-chef.box"


  config.vm.box = "opscode_ubuntu-12.04_chef-provisionerless"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-12.04_chef-provisionerless.box"

  config.vm.network :forwarded_port, guest: 80, host: 8200

  config.omnibus.chef_version = :latest
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = 'cookbooks'
 
    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
  end
end
