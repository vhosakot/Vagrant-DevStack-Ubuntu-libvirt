# Vagrant-DevStack-Ubuntu-libvirt

Vagrantfile and steps to install Vagrant in Linux (running libvirt/qemu)
and deploy an Ubuntu 14.04 (trusty64) VM with 32 GB RAM, 8 CPUs, hostname
'devstack-ubuntu-trusty', and DevStack repo cloned into
/home/vagrant/devstack/ from https://git.openstack.org/openstack-dev/devstack.

1.  Copy Vagrantfile

2.  Run the steps in vagrant_installation_steps.txt

3.  vagrant up --provider=libvirt

4.  vagrant ssh

    DevStack will be at /home/vagrant/devstack/

5.  vagrant destroy
