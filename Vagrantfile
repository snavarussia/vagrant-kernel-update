# Define virtual machine configuration
MACHINES = {
  # Specify VM name "kernel update"
  :"kernel-update" => {
              # Define VM box image
              :box_name => "ubuntu/focal64",
              # Specify box version
              :box_version => "20240821.0.1",
              # Set number of CPU cores
              :cpus => 1,
              # Set allocated RAM in megabytes
              :memory => 1024,
            }
}

Vagrant.configure("2") do |config|
  MACHINES.each do |boxname, boxconfig|
      # Disable shared folder sync to the VM
      config.vm.synced_folder ".", "/vagrant", disabled: true
      # Apply VM configuration
      config.vm.define boxname do |box|
      box.vm.box = boxconfig[:box_name]
      box.vm.box_version = boxconfig[:box_version]
      box.vm.host_name = boxname.to_s
      box.vm.provider "virtualbox" do |v|
        v.memory = boxconfig[:memory]
        v.cpus = boxconfig[:cpus]
      end
    end
  end
end
