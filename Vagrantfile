Vagrant.configure('2') do |config|
  config.vm.box      = 'precise32'
  config.vm.box_url  = 'http://files.vagrantup.com/precise32.box'
  config.vm.hostname = 'rails-dev-box'

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.network :private_network, ip: "10.0.1.5"

  config.vm.synced_folder "clinica/", "/home/vagrant/projects/clinica", :nfs => true
  config.vm.synced_folder "gestorgen/", "/home/vagrant/projects/gestorgen", :nfs => true

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = 'puppet/manifests'
    puppet.module_path    = 'puppet/modules'
  end
end
