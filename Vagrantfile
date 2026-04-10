Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/focal64"
    master.vm.hostname = "k8s-master"
    master.vm.network "private_network", ip: "192.168.56.101"
    master.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
  end

  config.vm.define "worker" do |worker|
    worker.vm.box = "ubuntu/focal64"
    worker.vm.hostname = "k8s-worker"
    worker.vm.network "private_network", ip: "192.168.56.102"
    worker.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
  end

end