VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "generic/centos7"
  # config.vm.hostname = "moringa.test"
  #config.vm.network :private_network, ip: "192.168.56.7"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  # server1.
  config.vm.define "server1" do |sv|
    config.vm.hostname = "moringa.test"
    config.vm.network :private_network, ip: "192.168.60.8"
  end
  
  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "apache.yml"
  end
end