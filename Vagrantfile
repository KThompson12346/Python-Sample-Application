# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
required_plugins = ["vagrant-hostsupdater", "vagrant-berkshelf"]
required_plugins.each do |plugin|
  unless Vagrant.has_plugin?(plugin)
    # User vagrant plugin manager to install plugin, which will automatically refresh plugin list
    puts "Installing vagrant plugin #{plugin}"
    Vagrant::Plugin::Manager.instance.install_plugin plugin
    puts "Installed vagrant plugin #{plugin}"
  end
end


Vagrant.configure("2") do |config|
  config.vm.define "app" do |app|
    config.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.72.1"
    app.hostsupdater.aliases = ["python.local"]
    app.vm.synced_folder "Python-Sample-Application", "/home/ubuntu/python-app"

  config.vm.define "nginx" do
    config.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.72.2"

    end
  end







end
