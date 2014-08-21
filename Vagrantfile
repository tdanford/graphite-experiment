Vagrant.configure("2") do |config|
  config.vm.box = 'lucid32'
  config.omnibus.chef_version = :latest
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = 'cookbooks'
 
    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
  end
end
