# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

branch=`git branch`.gsub(/^\* /,'')
Vagrant.configure(2) do |config|
  config.vm.box = "azizshamim/jessie64"

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y git curl bzip2 zip xz-utils gnupg kpartx dosfstools binutils
    git clone file:///vagrant
    cd vagrant; git checkout #{branch}
  SHELL
end
