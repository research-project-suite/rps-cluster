Vagrant.configure(2) do |config|

  config.vm.synced_folder '.', '/vagrant', disabled: true

  config.vm.box = "debian/testing64"

  config.vm.define "node1" do |node|
    node.vm.hostname = "node1"
    node.vm.network "private_network", ip: "192.168.59.11"
  end

  config.vm.define "node2" do |node|
    node.vm.hostname = "node2"
    node.vm.network "private_network", ip: "192.168.59.12"
  end
  config.vm.define "node3" do |node|
    node.vm.hostname = "node3"
    node.vm.network "private_network", ip: "192.168.59.13"
    node.vm.provision "ansible" do |ansible|
      ansible.limit = 'all'
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "vagrant-provision.yaml"
      ansible.groups = {
        "lxd_servers" => [
          "node1",
          "node2",
          "node3",
        ],
      }
      ansible.host_vars = {
        "node1" => {
          "lxd_server_name" => "192.168.59.11",
        },
        "node2" => {
          "lxd_server_name" => "192.168.59.12",
        },
        "node3" => {
          "lxd_server_name" => "192.168.59.13",
        },
      }
    end
  end

end
