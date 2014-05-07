#biemond-orawls-vagrant-oim

Oracle Access Manager, Oracle Identity Manager

The reference implementation of https://github.com/biemond/biemond-wls  

uses a CentOS 6.5 vagrant box for Virtualbox which includes puppet 3.4.2

##Delivers
- creates a patched 10.3.6.06 WebLogic Server with OIM, OAM 11.1.2.1 ( oimapp )
- creates a Oracle EE database 12c with OIM,OAM RCU Repository ( oimdb )

##Software
Add the all the Oracle binaries to /software, edit Vagrantfile and update
- oimapp.vm.synced_folder "/Users/edwin/software", "/software"
- oimdb.vm.synced_folder "/Users/edwin/software", "/software"

###Java
- jdk-7u45-linux-x64.tar.gz

###WebLogic
- wls1036_generic.jar
- p17071663_1036_Generic.zip ( BSU patch 10.3.6.0.6 )

###RCU from edelivery
- V37476-01.zip ( 11.1.2.1 )

###FMW SOA Suite
- ofm_soa_generic_11.1.1.6.0_disk1_1of2.zip ( SOA Suite 11.1.1.6.0  )
- ofm_soa_generic_11.1.1.6.0_disk1_2of2.zip ( SOA Suite 11.1.1.6.0  )
- p16702086_111160_Generic.zip ( SOA Suite 11.1.1.6.0  OPatch )
- p16366204_111160_Generic.zip ( SOA Suite 11.1.1.6.0  OPatch )

### OIM & OAM
- V37472-01_1of2.zip ( OIM & OAM 11.1.2.1 )
- V37472-01_2of2.zip ( OIM & OAM 11.1.2.1 )
- p17086188_111210_Generic.zip ( OIM & OAM 11.1.2.1  OPatch )

###Database 11.2.0.4
- p13390677_112040_Linux-x86-64_1of2.zip
- p13390677_112040_Linux-x86-64_2of7.zip

##Running from Vagrant

Download the latest version of Vagrant & Oracle Virtualbox

### oim db server  
vagrant up oimdb

### oim application server  
vagrant up oimapp
