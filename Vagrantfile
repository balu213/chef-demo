# -*- mode: ruby -*-
# vi: set ft=ruby :
 Vagrant.configure('2') do |config|
 config.vm.box = 'precise'
 config.vm.box_url = 'http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box'
 config.vm.network :private_network, ip: '192.168.33.10'

config.vm.provider :virtualbox do |vb|
     vb.customize ['modifyvm', :id, '--memory', 1024, '--cpus', '1']
 end
 config.vm.provision :chef_client do |chef|
   chef.node_name = 'balu213'
   chef.chef_server_url = 'https://api.chef.io/organizations/baluchef'
   chef.validation_key_path = '/Users/admin/Downloads/chef-repo/.chef/baluchef-validator.pem'
   chef.validation_client_name = 'baluchef-validator'
   chef.run_list = [ "recipe[apache2::default]" ]
 end
end
