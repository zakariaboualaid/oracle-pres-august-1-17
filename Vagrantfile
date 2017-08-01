VAGRANTFILE_API_VERSION = '2'.freeze

Vagrant.configure(VAGRANTFILE_API_VERSION) do |c|
  c.vm.define :oracle_puppet_vm do |config|
    config.vm.box = 'ubuntu/trusty64'

    config.vm.network 'forwarded_port', guest: 80, host: 3000
    config.vm.hostname = 'ubuntu-14.oracle'

    config.vm.network 'private_network', ip: '192.168.20.60'
    config.ssh.forward_agent = false

    config.vm.synced_folder './puppet', '/etc/puppetlabs/code'

    config.vm.provider 'virtualbox' do |vb|
      vb.customize ['modifyvm', :id, '--memory', '2400']
    end
  end
end
