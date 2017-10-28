Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.synced_folder ".", "/vagrant", type: "sshfs"
  config.vm.provision "ansible_local" do |ansible|
    ansible.config_file = "ansible-vagrant.cfg"
    ansible.playbook = "vagrant.yml"
  end
end
