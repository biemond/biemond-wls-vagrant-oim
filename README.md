biemond-orawls-vagrant-oim
==========================

Oracle Access Manager, Oracle Identity Manager

The reference implementation of https://github.com/biemond/biemond-wls  

uses CentOS 6.5 box with puppet 3.4.2

creates a patched 10.3.6.06 WebLogic Server with OIM, OAM 11.1.2.1 ( oimapp )

creates a Oracle EE database 12c with OIM,OAM RCU Repository ( oimdb )

Add the all the Oracle binaris to /software, edit Vagrantfile and update
- oimapp.vm.synced_folder "/Users/edwin/software", "/software"
- oimdb.vm.synced_folder "/Users/edwin/software", "/software"

used the following software
- jdk-7u45-linux-x64.tar.gz

weblogic 10.3.6
- wls1036_generic.jar
- p17071663_1036_Generic.zip ( BSU patch 10.3.6.0.6 )

RCU from edelivery
- V37476-01.zip ( 11.1.2.1 )

FMW
- ofm_soa_generic_11.1.1.6.0_disk1_1of2.zip ( SOA Suite 11.1.1.6.0  )
- ofm_soa_generic_11.1.1.6.0_disk1_2of2.zip ( SOA Suite 11.1.1.6.0  )
- p16702086_111160_Generic.zip ( SOA Suite 11.1.1.6.0  OPatch )
- p16366204_111160_Generic.zip ( SOA Suite 11.1.1.6.0  OPatch )
- V37472-01_1of2.zip ( OIM & OAM 11.1.2.1 )
- V37472-01_2of2.zip ( OIM & OAM 11.1.2.1 )
- p17086188_111210_Generic.zip ( OIM & OAM 11.1.2.1  OPatch )

Database 11.2.0.4
- p13390677_112040_Linux-x86-64_1of2.zip
- p13390677_112040_Linux-x86-64_2of7.zip
- p13390677_112040_Linux-x86-64_3of2.zip
- p13390677_112040_Linux-x86-64_4of7.zip
- p13390677_112040_Linux-x86-64_5of2.zip
- p13390677_112040_Linux-x86-64_6of7.zip
- p13390677_112040_Linux-x86-64_7of2.zip

# oimdb  
vagrant up oimdb

# oimapp server  
vagrant up oimapp


