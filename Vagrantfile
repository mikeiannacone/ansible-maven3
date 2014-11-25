VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/debian-7.6"
  config.vm.host_name = "ansible-test"
  config.vm.network :private_network, ip: "192.168.33.15"
  config.vm.synced_folder "../vagrant", "/vagrant"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "../test_role.yml"
    ansible.inventory_path = "inventory"
    ansible.host_key_checking = false
    ansible.verbose = "v"
  end
end