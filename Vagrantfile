# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	Vagrant.require_version ">= 1.6.0"
	
	# use omnibus to install latest chef
	config.omnibus.chef_version = "latest"
	# enable berkshelf support
	config.berkshelf.enabled = true
	
	# hostmanager plugin
	config.hostmanager.enabled = true
	config.hostmanager.manage_host = true
	
	config.vm.box = "chef/ubuntu-14.04"
	config.vm.synced_folder "C:/AppDevData/Software/packages", "/software", :mount_options => ["ro"] # software package folder
	
	config.vm.define "aemdev" do |aemdev|
	
		aemdev.ssh.forward_x11 = true
		
		aemdev.vm.network "forwarded_port", guest: 4502, host: 4502
		
		aemdev.vm.provider "virtualbox" do |v|
		
			v.memory = 2048
			v.cpus = 2
		end
		
		aemdev.vm.provision "chef_solo" do |chef|
		
			chef.log_level = "info"
			
			chef.roles_path = "roles"
			chef.environments_path = "environments"
			
			chef.environment = "aem-local"
			chef.add_role "aem-developer"
		end
		
	end
  
	config.vm.define "lampdev" do |lampdev|
	
		lampdev.ssh.forward_x11 = true
		
		lampdev.vm.network "forwarded_port", guest: 8080, host: 8080
				
		lampdev.vm.provision "chef_solo" do |chef|
		
			chef.log_level = "info"
			
			chef.roles_path = "roles"
			chef.environments_path = "environments"
			  
			chef.json = {
				"chef-devstax" => {
					"apache" => {
						"vhosts" =>  [
							{
								"name" => "lampdev",
								"phpinfo" => true
							}
						]
					}
				}
			}
			chef.environment = "lamp-local"
			chef.add_role "lamp-developer"
			chef.add_recipe "recipe[chef-devstax::vhosts]"
		end
		
	end
	
end
