# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "oimapp" , primary: true do |oimapp|
    oimapp.vm.box = "centos-6.5-x86_64"
    #admin.vm.box_url ="/Users/edwin/Downloads/centos-6.5-x86_64.box"
    oimapp.vm.box_url = "https://dl.dropboxusercontent.com/s/np39xdpw05wfmv4/centos-6.5-x86_64.box"

    oimapp.vm.hostname = "oimapp.example.com"

    #oimapp.vm.synced_folder "."                    , "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    #oimapp.vm.synced_folder "/Users/edwin/software", "/software"
    oimapp.vm.synced_folder "."                    , "/vagrant" , type: "nfs"
    oimapp.vm.synced_folder "/Users/edwin/software", "/software", type: "nfs"

  
    oimapp.vm.network :private_network, ip: "10.10.10.10"
  
    oimapp.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "3500"]
      vb.customize ["modifyvm", :id, "--name"  , "oimapp"]
    end
  
    oimapp.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml"
    
    oimapp.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "oimapp.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"
  
      puppet.facter = {
        "environment"                     => "development",
        "vm_type"                         => "vagrant",
      }
      
    end
  
  end

  config.vm.define "oimdb" , primary: true do |oimdb|
    oimdb.vm.box = "centos-6.5-x86_64"
    oimdb.vm.box_url = "https://dl.dropboxusercontent.com/s/np39xdpw05wfmv4/centos-6.5-x86_64.box"

    oimdb.vm.hostname = "oimdb.example.com"
    oimdb.vm.network :private_network, ip: "10.10.10.5"

    #oimdb.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    #oimdb.vm.synced_folder "/Users/edwin/software", "/software"
    oimdb.vm.synced_folder ".", "/vagrant", type: "nfs"
    oimdb.vm.synced_folder "/Users/edwin/software", "/software", type: "nfs"
  
    oimdb.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm"     , :id, "--memory", "2000"]
      vb.customize ["modifyvm"     , :id, "--name"  , "oimdb"]
    end

  
    oimdb.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml"
    
    oimdb.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "oimdb.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"
  
      puppet.facter = {
        "environment" => "development",
        "vm_type"     => "vagrant",
      }
      
    end
  
  end  



end
