Vagrant.configure("2") do |config|
  config.vm.box = "centos/8"
  config.vm.provision "shell", path: "vb-guest-additions.sh"
  config.vm.provision "podman" do |d|
    d.build_image "/vagrant/app", args: "-t 'webserver'"
    d.run "webserver", args: "-p 8000:8000"
  end
  config.vm.network "forwarded_port", guest: 8000, host: 8000
end
