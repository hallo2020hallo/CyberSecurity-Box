<img src="https://github.com/CyberAndi/CyberSecurity-Box/blob/Version2/CyberSecurityBox.jpg" alt="Logo" width="300px"></img>
# CyberSecurity-Box<h3>(inkl. Ad Blocker, UnBound (DNS), Tor or optional Pi-Hole5 (incl. DB) and ntopng)</h3>
<p>
<ul><li>
  <h3>Installation on OpenWRT-Router - Alternative 1</h3>
  use SSH or Putty for Installation and type the following code.<br><br>
  <pre><code>ssh [ip-address of OpenWRT]</code></pre>
  User: <i><b>root</b></i>
  <br>
  Password: <i><b></b></i><br><br>
  Change the Password with<br><br>
  <pre><code>passwd
[newpassword]
[newpassword]</code></pre>
  Don´t forget to note the <i><b>newpassword</b></i>.<br>
  <br>
  copy the sourcecode from <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/CyberAndi-Pi-Hole-5/tor_unbound_openwrt.txt">https://github.com/CyberAndi/CyberSecurity-Box/blob/CyberAndi-Pi-Hole-5/tor_unbound_openwrt.txt</a> and insert and run in ssh.
  </li>
  <li>
  <h3>Installation CyberSecurityBox (RasPi) - Alternative 2</h3>
  You need a Raspberry Pi and a SD-Card with 8 GByte or more.
  Use a blank <b><a href="https://www.raspberrypi.org/downloads/raspbian/">Raspbian-SD-Card-Image</a></b> or 
  <b>CyberSecurityBox_2.img</b> is the Pi-Hole, UnBound and torrc with a ready-to-use Image.
  <br>Install one of this with <b><a href="https://www.balena.io/etcher/">balenaEtcher</a></b> on a SD-Card. <br>Insert the SD-Card in the RasPi. And use SSH or Putty for Installation and type the following code.<br><br>
  <pre><code>ssh [ip-address of RasPi]</code></pre>
  User: <i><b>pi</b></i>
  <br>
  Password: <i><b>raspberry</b></i><br><br>
  Change the Password with<br><br>
  <pre><code>passwd
[newpassword]
[newpassword]</code></pre>
  Don´t forget to note the <i><b>newpassword</b></i>.<br>
  <br>
  <pre><code>sudo su
apt-get update
apt-get upgrade -y</code></pre>
  <ol>
    <li>
<h4>Type for Installation</h4>
     <pre><code>apt-get install tor unbound privoxy ntopng postfix iptables-persistent netfilter-persistent -y
curl -sSL https://install.pi-hole.net | bash</code></pre>
     and follow the messages on the screen.<br>
    </li>
    <li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/CyberAndi-Pi-Hole-5/pi-hole-teleporter_2020-06-07_09-38-48.tar.gz">pi-hole-teleporter_2020-06-07_09-38-48.tar.gz</a></h4>
      Is the newest Version with <b>PiHole 5.0 and DataBase Support</b>. It includes the Porn-, Ad- and Tracking-Blocking.
    </li>
    <li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/raw/master/pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz">pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz</a></h4> inludes White- and Blacklist (Advertisement and Maleware). <b> Until Pi-Hole 4 and smaller</b></li>
    <li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/raw/master/pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz">pi-hole-teleporter_CyberSecurity_Box_2018-12-20_.tar.gz</a></h4> inludes White- and Blacklist (Advertisement, Maleware, Tracking and Porn).<b> Until Pi-Hole 4 and smaller</b></li>
    <li>
    <h4>The Pi-Hole 4 <a href="https://github.com/CyberAndi/CyberSecurity-Box/raw/master/regex.list">regex.list</a></h4> includes Blacklist (Advertisment, Maleware, Tracking and Porn) with over 40% blocking rate.<br> In pi-hole-teleporter_2020-06-07_09-38-48.tar.gz is this included for Pi-Hole5.
  <pre><code>service pihole-FTL stop
service unbound stop
service privoxy stop
service tor stop
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/whitelist_Alexa_Google_Home_Smarthome.txt > whitelist.txt
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/tor/torrc > torrc
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/unbound/root.hints > root.hints
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/unbound/unbound.conf > unbound.conf
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/unbound/unbound.conf.d/test.conf > unbound_tor_pihole.conf
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/unbound.sh > unbound.sh
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/privoxy/config > config
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/boxed-bg.jpg > boxed-bg.jpg
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/boxed-bg.png > boxed-bg.png
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/blockingpage.css > blockingpage.css
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/AdminLTE.min.css > AdminLTE.min.css
curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/Version2/skin-blue.min.css > skin-blue.min.css
<br>
cp whitelist.txt /etc/pihole/whitelist.txt
cp root.hints /etc/unbound/root.hints
cp unbound.conf /etc/unbound/unbound.conf
cp unbound.sh /etc/cron.weekly
cp unbound_tor_pihole.conf /etc/unbound/unbound.conf.d/unbound_tor_pihole.conf -r -v
cp config /etc/privoxy/config
cp boxed-bg.jpg /var/www/html/admin/img/boxed-bg.jpg
cp *.css /var/www/html/admin/style/vendor/
cp blockingpage.css /var/www/html/pihole/
<br>
service tor start
service privoxy start
service unbound start
service pihole-FTL start</code></pre>
   </li>
  </ol>
  <li>
  <h3>(optional) Configuration of the AVM FRITZ!Box with Presets for Security and Port-List - Option for Alternative 2 Pi_Hole</h3>
<h4>This <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/master/CyberSecurityBox.zip">zip-File</a></h4> includes a AVM FRITZ!Box-Export-File for FRITZ OS 6.80 and above. It includes Firewall-Rules for Amazon Alexa/Echo, Google Assistens, NAS, MS-Servers etc.<br>
  <img src="Schema.PNG" width="450px"></img>
  </li>
</ul></p>
<p>
For more Information in german visit https://www.cyberandi.de/Smarthome
</p>
<hr>
<center>Contact: <a href="mailto:cyberandi@outlook.de">cyberandi@outlook.de</a> - Website: https://www.cyberandi.de</center>
</hr>
