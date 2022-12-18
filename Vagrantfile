Vagrant.configure(2) do |config|

    config.vm.box = "debian/testing64"

    config.vm.define "node1" 
    config.vm.define "node2" 
    config.vm.define "node3"

    config.vm.define "rpx" do |define|

        define.vm.provision "ansible" do |ansible|
            ansible.limit = 'all'
            ansible.playbook = "dev-env.yaml"
      
            ansible.groups = {
              "cluster_nodes" => [
                "node1",
                "node2",
                "node3",
              ],
              "reverse_proxies" => ["rpx"]
            }
        end
    end

end
