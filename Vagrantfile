# -*- mode: ruby -*-
# vi: set ft=ruby :

# wpkit version: 0.0.1

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Configuration options for the VirtualBox provider.
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

  # Configuration options for the Parallels provider.
  config.vm.provider :parallels do |v|
    v.update_guest_tools = true
    v.optimize_power_consumption = false
    v.memory = 1024
  end

  # Configuration options for the VMware Fusion provider.
  config.vm.provider :vmware_fusion do |v|
    v.vmx["memsize"] = "1024"
    v.vmx["numvcpus"] = "2"
  end

  # VM OS - Ubuntu 14.04 x64
  config.vm.box = "ubuntu/trusty64"

  # The Parallels Provider uses a different naming scheme.
  config.vm.provider :parallels do |v, override|
    override.vm.box = "parallels/ubuntu-14.04"
  end

  # The VMware Fusion Provider uses a different naming scheme.
  config.vm.provider :vmware_fusion do |v, override|
    override.vm.box = "netsensia/ubuntu-trusty64"
  end

  if Vagrant.has_plugin?("vagrant-cachier")
    # Configure cached packages to be shared between instances of the same base box.
    # More info on http://fgrehm.viewdocs.io/vagrant-cachier/usage
    config.cache.scope = :box

    # OPTIONAL: If you are using VirtualBox, you might want to use that to enable
    # NFS for shared folders. This is also very useful for vagrant-libvirt if you
    # want bi-directional sync
    config.cache.synced_folder_opts = {
      type: :nfs,
      # The nolock option can be useful for an NFSv3 client that wants to avoid the
      # NLM sideband protocol. Without this option, apt-get might hang if it tries
      # to lock files needed for /var/cache/* operations. All of this can be avoided
      # by using NFSv4 everywhere. Please note that the tcp option is not the default.
      mount_options: ['rw', 'vers=3', 'tcp', 'nolock']
    }
    # For more information please check http://docs.vagrantup.com/v2/synced-folders/basic_usage.html
  end

  # SSH Agent Forwarding
  config.ssh.forward_agent = true

  # VM Hostname & network (with hostsupdater)
  config.vm.network :private_network, ip: "192.168.3.10"
  config.vm.hostname = "www.wpkit.dev"

  # Create a forwarded port mapping which allows access to a specific port
  config.vm.network "forwarded_port", guest: 80, host: 8000

  # Share folders to the guest VM.
  config.vm.synced_folder "www", "/var/www/wpkit.dev", owner: "www-data", group: "www-data"

  # Install software for VM
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/vagrant.yml"
  end
end
