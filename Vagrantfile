# Purpose: Vagrantfile for a multi-machine setup for a Virtual Home Lab
# Author: Chris Wagner
# Date: June 2023

# top level domain
domain = "midwest.us"

# Define the boxes
boxes = [
  { :hostname => "missouri", :ip => "192.168.127.2", :box => "centos/7", :version => "2004.01" },
  { :hostname => "kansas", :ip => "192.168.127.3", :box => "generic/ubuntu1804", :version => "4.2.16" },
  { :hostname => "nebraska", :ip => "192.168.127.4", :box => "centos/7", :version => "2004.01" },
]

Vagrant.configure("2") do |config|
  # Configures multiple boxes
  boxes.each do |box|
    
    # Dynamically define the box configuration
    config.vm.define box[:hostname] do |box_config|
      box_config.vm.box = box[:box]
      box_config.vm.box_version = box[:version] ? box[:version] : nil

      box_config.vm.hostname = "#{box[:hostname]}.#{domain}"
      box_config.vm.network :private_network, ip: box[:ip], hostname: true

      box_config.vm.post_up_message = "The #{box[:hostname]}.#{domain} box is now ready to use!\n" \
        "Use `vagrant ssh #{box[:hostname]}` to access the box."
    end

    # Use provisioning to run a script on the box after it is created
    # Example: Using a shell script or an Ansible playbook
    # config.vm.provision "shell", "path/to/script.sh"
  end
end
