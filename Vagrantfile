# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.network "forwarded_port", guest: 80, host: 8000
  config.vm.provision :shell, :path => "bootstrap.sh"

  config.vm.synced_folder "./", "/var/www", create: true, group: "www-data", owner: "www-data", :mount_options => ["dmode=777,fmode=777"]

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
end
