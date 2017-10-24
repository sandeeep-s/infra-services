
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.define "infra"
  config.vm.network "forwarded_port", guest: 9050, host: 9050
  config.vm.network "forwarded_port", guest: 9990, host: 9990
  config.vm.provision "docker" do |d|
    d.run "jboss/keycloak",
      args: "-d -p 9990:9990 -p 9050:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin"
  end
end
