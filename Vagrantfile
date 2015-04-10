# Commands to run on Ubuntu guest
$script = <<SCRIPT
sudo apt-get -y update
sudo apt-get -y upgrade
sudo apt-get -y install git
sudo apt-get -y install git-review
git clone https://git.openstack.org/openstack-dev/devstack
sudo chmod -R 777 devstack/
cp -f local.conf devstack/
rm -rf local.conf
SCRIPT

Vagrant.configure("2") do |config|

  config.vm.define :my_vm do |machine|

    machine.vm.box = "trusty64"
    machine.vm.hostname = "devstack-ubuntu-trusty"

    # Section for libvirt provider
    machine.vm.provider :libvirt do |domain|
      # 32 GB RAM
      domain.memory = 32768
      # 8 CPUs
      domain.cpus = 8
    end

    # Copy Vagrant-DevStack-Ubuntu-libvirt/local.conf from host to guest
    machine.vm.provision "file", source: "local.conf", destination: "local.conf"

    # Run script on guest
    machine.vm.provision :shell, inline: $script

    # Standup DevStack on Ubuntu guest
    machine.vm.provision :shell, inline: "cd devstack ; ./stack.sh", privileged: false

  end

end
