Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu-64-chef-11"
  config.vm.box_url = "http://grahamc.com/vagrant/ubuntu-12.04-omnibus-chef.box"
  config.omnibus.chef_version = :latest
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = 'cookbooks'
 
    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
  end
end
