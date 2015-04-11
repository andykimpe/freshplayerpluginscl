# freshplayerpluginscl
scl centos 6 for https://github.com/i-rinat/freshplayerplugin/

compile freshplayerplugin on centos 6

Capture Wallpaper Centos 6 x64 Server Desktop (French Version) using x2go

<img src="http://img15.hostingpics.net/pics/575925Capturedu20150409221606.png" border="0"  />


# 1 Install dependency or stable version

<code>sudo yum -y install epel-release</code>

<code>sudo wget https://github.com/andykimpe/freshplayerpluginscl/raw/master/el6/freshplayerpluginscl.repo -P /etc/yum.repos.d</code>

<code>sudo yum -y update</code>

# 1.1 Install stable version 0.2.3

<code>sudo yum -y install freshplayerplugin</code>

# 1.2 Install dependency

<code>sudo yum -y install freshplayerpluginscl</code>

# 2 Compile

<code>git clone https://github.com/i-rinat/freshplayerplugin.git</code>

<code>cd freshplayerplugin</code>

<code>scl enable freshplayerpluginscl 'cmake .'</code>

<code>scl enable freshplayerpluginscl 'make'</code>

# 3 install module and config

install config for 64 bit

<code>sed -i 's|/opt/google/chrome/PepperFlash/libpepflashplayer.so|/usr/lib64/chromium/PepperFlash/libpepflashplayer.so|' "data/freshwrapper.conf.example"</code>

<code>sudo cp data/freshwrapper.conf.example /etc/freshwrapper.conf</code>

install config for 32 bit

<code>sed -i 's|/opt/google/chrome/PepperFlash/libpepflashplayer.so|/usr/lib/chromium/PepperFlash/libpepflashplayer.so|' "data/freshwrapper.conf.example"</code>

<code>sudo cp data/freshwrapper.conf.example /etc/freshwrapper.conf</code>

install module for 64 bit

<code>sudo rm -f /usr/lib64/mozilla/plugins/libfreshwrapper-pepperflash.so /usr/lib64/freshplayerplugin/libfreshwrapper-pepperflash.so</code>

<code>sudo mkdir -p /usr/lib64/freshplayerplugin/</code>

<code>sudo cp libfreshwrapper-pepperflash.so /usr/lib64/freshplayerplugin/</code>

<code>sudo ln -s /usr/lib64/freshplayerplugin/libfreshwrapper-pepperflash.so /usr/lib64/mozilla/plugins/libfreshwrapper-pepperflash.so</code>

<code>sudo chmod 0755 /usr/lib64/mozilla/plugins/libfreshwrapper-pepperflash.so</code>

<code>sudo chmod 0755 /usr/lib64/freshplayerplugin/libfreshwrapper-pepperflash.so</code>

install module for 32 bit

<code>sudo rm -f /usr/lib/mozilla/plugins/libfreshwrapper-pepperflash.so /usr/lib/freshplayerplugin/libfreshwrapper-pepperflash.so</code>

<code>sudo mkdir -p /usr/lib/freshplayerplugin/</code>

<code>sudo cp libfreshwrapper-pepperflash.so /usr/lib/freshplayerplugin/</code>

<code>sudo ln -s /usr/lib/freshplayerplugin/libfreshwrapper-pepperflash.so /usr/lib/mozilla/plugins/libfreshwrapper-pepperflash.so</code>

<code>sudo chmod 0755 /usr/lib/mozilla/plugins/libfreshwrapper-pepperflash.so</code>

<code>sudo chmod 0755 /usr/lib/freshplayerplugin/libfreshwrapper-pepperflash.so</code>

# 4 Install Pepper-Flash

<code>sudo yum -y install chromium-pepper-flash</code>



100 % work on centos 6.6 64 bit
