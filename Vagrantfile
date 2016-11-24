Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/ubuntu1604-desktop"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "4096"
  end
  
  config.vm.provision "shell", path: "bootstrap.sh"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "setup.yml"
    ansible.ask_sudo_pass = true
    ansible.extra_vars = "@config.json"
  end
end
