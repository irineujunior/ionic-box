# -*- mode: ruby -*-

# vi: set ft=ruby :

Vagrant.configure(2) do |config|
	config.vm.box = "drifty/ionic-android"
	config.vm.hostname = "ionic-android" # No Spaced Allowed

	config.vm.boot_timeout = 600
	config.vm.network :forwarded_port, host: 8100, guest: 8100
	config.vm.network :forwarded_port, host: 35729, guest: 35729
	# Mapeamento no Windows
	# config.vm.synced_folder "c:\\CodeIonic", "/home/vagrant/CodeIonic"
	config.vm.synced_folder "../CodeIonic", "/home/vagrant/CodeIonic"

	config.vm.provider "virtualbox" do |vb|
		vb.gui = true
		vb.customize ["modifyvm", :id, "--vram", "128"]
		vb.customize ["modifyvm", :id, "--usb", "on"]
		vb.customize ["usbfilter", "add", "0", "--target", :id, "--name", "android", "--vendorid", "0x18d1"]
		vb.memory = 2048
		vb.cpus = 2
		vb.name = "IonicBox"
	   
		# Descomente o item abaixo no Windows	
		# vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
	end
end
