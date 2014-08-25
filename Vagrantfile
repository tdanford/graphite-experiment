Vagrant.configure("2") do |config|
  config.vm.network :forwarded_port, guest: 80, host: 8200
  config.vm.network :forwarded_port, guest: 2003, host: 2003

  config.vm.provider :virtualbox do |vb, override|
    override.vm.box = "opscode_ubuntu-12.04_chef-provisionerless"
    override.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-12.04_chef-provisionerless.box"
  end

  config.vm.provider :aws do |aws, override|
    override.vm.box = "aws-dummy"
    override.vm.box_url = "https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box"
    # vagrant-ssh: 22
    # vagrant-graphite: 80, 2003
    aws.security_groups = ["vagrant-ssh", "vagrant-graphite"]
    aws.ami = "ami-b8b061d0"
  end

  config.omnibus.chef_version = :latest
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = 'cookbooks'
 
    chef.add_recipe 'apt'
    chef.add_recipe 'graphite'
    chef.add_recipe 'graphite::apache'
  end
end
