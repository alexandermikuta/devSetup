Vagrant.configure(2) do |config|
  config.vm.box = "zbynekstava/ubuntudesktop21.10"
  #config.vm.box = "wouterspaans1/ubuntu-21.04-desktop"
  config.vm.box_version = "1.0.0"

  config.vm.provider "virtualbox" do |vb|
  #config.vm.provider "vmware_desktop" do |vb|
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
