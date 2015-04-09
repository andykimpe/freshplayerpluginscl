# freshplayerpluginscl
scl centos 6 for https://github.com/i-rinat/freshplayerplugin/

compile freshplayerplugin on centos 6

sudo yum -y install epel-release

sudo wget https://github.com/andykimpe/freshplayerpluginscl/raw/master/el6/freshplayerpluginscl.repo -P /etc/yum.repos.d

sudo yum -y update

sudo yum -y install freshplayerpluginscl

git clone https://github.com/i-rinat/freshplayerplugin.git

cd freshplayerplugin

scl enable freshplayerpluginscl 'cmake .'

scl enable freshplayerplugin 'make'

work on 64 bit
