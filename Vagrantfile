$script = <<SCRIPT
sudo apt-get -y update
sudo apt-get -y upgrade
sudo apt-get -y install git
git clone https://git.openstack.org/openstack-dev/devstack
SCRIPT

Vagrant.configure("2") do |config|

  config.vm.define :my_vm do |machine|

    machine.vm.box = "trusty64"
    machine.vm.hostname = "devstack-ubuntu-trusty"

    machine.vm.provider :libvirt do |domain|
      domain.memory = 32768
      domain.cpus = 8
    end

    machine.vm.provision :shell, inline: $script

  end

end
