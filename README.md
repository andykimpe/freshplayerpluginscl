# freshplayerpluginscl
scl centos 6 for https://github.com/i-rinat/freshplayerplugin/

compile freshplayerplugin on centos 6

# 1 Install dependency

<code>sudo yum -y install epel-release</code>

<code>sudo wget https://github.com/andykimpe/freshplayerpluginscl/raw/master/el6/freshplayerpluginscl.repo -P /etc/yum.repos.d</code>

<code>sudo yum -y update</code>

<code>sudo yum -y install freshplayerpluginscl</code>

# Compile

<code>git clone https://github.com/i-rinat/freshplayerplugin.git</code>

<code>cd freshplayerplugin</code>

<code>scl enable freshplayerpluginscl 'cmake .'</code>

<code>scl enable freshplayerpluginscl 'make'</code>

# install module and config

<code>sudo cp data/freshwrapper.conf.example /etc/freshwrapper.conf</code>

install module for 64 bit

<code>sudo cp libfreshwrapper-pepperflash.so /usr/lib64/mozilla/plugins</code>

install module for 32 bit

<code>sudo cp libfreshwrapper-pepperflash.so /usr/lib/mozilla/plugins</code>

# Install Google Chrome Stable

<code>wget http://chrome.richardlloyd.org.uk/install_chrome.sh</code>

<code>chmod u+x install_chrome.sh</code>


<code>sudo ./install_chrome.sh</code>


100 % work on 64 bit


I have not had time to compile Box of 32 bit to be tested
