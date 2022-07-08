IMAGE_NAME = "bento/ubuntu-18.04"

NETWORK_SUB = "192.168.25."
START_IP = 200

cluster = {
  "master" => { :cpus => 2, :mem => 1024 }
}

Vagrant.configure("2") do |config|
  config.vm.box = IMAGE_NAME

  config.vm.define "ubuntu", primary: true do |master|
    master.vm.box = IMAGE_NAME
    master.vm.network "public_network", ip: "#{NETWORK_SUB}#{START_IP}"
    master.vm.hostname = "elastic"
    master.vm.provider "virtualbox" do |v|
      v.name = "ubuntu"
      v.gui = false
      v.memory = cluster['master'][:mem]
      v.cpus = cluster['master'][:cpus]
    end # end provider
  end
end