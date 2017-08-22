Vagrant.configure("2") do |config|

  config.vm.define :centos do |machine|

    machine.vm.box = "centos/7"

    machine.vm.hostname = "centos"

    machine.vm.provider :libvirt do |domain|
   
      domain.memory = 1024
      domain.cpus = 1
    end

    machine.vm.synced_folder "themes", "/srv/wordpress/wp-content/themes",
      mount_options: ["uid=1010,gid=1010"]

    machine.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "site.yml"
      ansible.limit = "all"
      ansible.groups = {
        "wordpress-server" => [ "centos" ]
      }
    end

  end

end

