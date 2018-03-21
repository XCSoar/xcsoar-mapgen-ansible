Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :machine
  end
  config.vm.synced_folder ".", "/vagrant", disabled: true
  if Vagrant.has_plugin?("vagrant-sshfs")
    config.vm.synced_folder ".", "/vagrant", type: "sshfs"
  else
    config.vm.synced_folder ".", "/vagrant", type: "nfs"
  end
  config.vm.provision "ansible_local" do |ansible|
    ansible.config_file = "ansible-vagrant.cfg"
    ansible.playbook = "vagrant.yml"
  end
end
