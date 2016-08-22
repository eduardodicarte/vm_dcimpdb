# -*- mode: ruby -*-
# vi: set ft=ruby :
 
VAGRANT_FILE_VERSION = 2

Vagrant.configure(VAGRANT_FILE_VERSION) do |config|
 
  config.vm.box = "puppetlabs/centos-7.0-64-puppet"
  
  config.vm.define :impdb do |impdb_config|
	impdb_config.vm.network :private_network, :ip => "192.168.43.10" 
	
	impdb_config.ssh.username   = 'root'
	impdb_config.ssh.password   = 'puppet'
	impdb_config.ssh.insert_key = 'true'
	
  end
  
  config.vm.provision "puppet" do |puppet|
  	puppet.environment_path = "environments"
  	puppet.environment 	= "development"
  	
  	puppet.facter = {
		"db_name"  => "impdb",
		"db_user"  => "imprt",
		"db_pass"  => "AvdWe&sd#",
		"sch_name" => "el"
	}
  end
end

