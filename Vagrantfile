# -*- mode: ruby -*-
# vi: set ft=ruby sw=2 ts=2 :

Vagrant::Config.run do |config|

  config.ssh.timeout = 60

  # Define a Ubuntu Server image (cloud) for the 12.04 release (precise)
  config.vm.define :precise do |precise_config|
    precise_config.vm.box = "precise-cloud-i386"
    precise_config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-i386-vagrant-disk1.box"
  end

  # Define a Ubuntu Server image (cloud) for the 12.10 release (quantal)
  config.vm.define :quantal do |quantal_config|
    quantal_config.vm.box = "quantal-cloud-i386"
    quantal_config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/quantal/current/quantal-server-cloudimg-i386-vagrant-disk1.box"
  end

  # Define a Ubuntu Server image (cloud) for the 13.04 release (raring)
  config.vm.define :raring do |raring_config|
    raring_config.vm.box = "raring-cloud-i386"
    raring_config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/raring/current/raring-server-cloudimg-i386-vagrant-disk1.box"
  end

  # Setup an apt cache if one is available
  if ENV.key? "VAGRANT_APT_CACHE"
    config.vm.provision :shell, :inline => "echo 'Acquire::http { Proxy \"#{ENV['VAGRANT_APT_CACHE']}\"; };' > /etc/apt/apt.conf"
  end
end
