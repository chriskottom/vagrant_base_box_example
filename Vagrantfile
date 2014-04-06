# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'precise64'
  config.berkshelf.enabled = true

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe 'apt'
    chef.add_recipe 'ruby_build'
    chef.add_recipe 'rbenv::system'
    chef.add_recipe 'rbenv::vagrant'
    chef.add_recipe 'chriskottom_precise64'  
    chef.json = {
      rbenv: {
        global: '2.1.1',
        rubies: [ '2.1.1' ],
        upgrade: true,
        gems: {
          '2.1.1' => [{ name: 'bundler' },
                      { name: 'main' },
                      { name: 'map' },
                      { name: 'open4' },
                      { name: 'multi_json' },
                      { name: 'net-ssh', version: '~> 2.2.0' },
                      { name: 'aws-sdk' },
                      { name: 'chef' },
                      { name: 'ohai' }]
        }
      },
  }
  end
end
