Vagrant::Config.run do |config|
  config.vm.box = 'lucid32'
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = 'cookbooks'
 
    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
  end
end
