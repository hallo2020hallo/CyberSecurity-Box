# CyberSecurity-Box
<p>
<h3>Configuration of the AVM FRITZ!Box an a SD-Card-Image with Pi-Hole, UnBound and Tor(rc) Presets for Security and Port-List</h3>
</p><p>
<ol>
  <li value="1"><h4>This <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/master/CyberSecurityBox.zip">zip-File</a> includes a AVM FRITZ!Box-Export-File for FRITZ OS 6.80 and above.</h4>
  It includes Firewall-Rules for Amazon 
  Alexa/Echo, NAS, MS-Servers etc.
  <br>
  <img src="Schema.PNG" width="450px"></img>

  </li>
  <li>
    
  <h3>Installation CyberSecurityBox</h3>
  You need a Raspberry Pi and a SD-Card with 8 GByte or more.
  Use a blank <b><a href="https://www.raspberrypi.org/downloads/raspbian/">Raspbian-SD-Card-Image</a></b> or 
  <b>CyberSecurityBox_2.img</b> is the Pi-Hole, UnBound and torrc ready to use Image
  <br>and Install one of this with <b><a href="https://www.balena.io/etcher/">balenaEtcher</a></b> on a SD-Card. Insert the SD-Card in the RasPi. And use SSH or Putty for Installation and type the following code.
  <pre><code>
  ssh [ip-address of RasPi]
  </code></pre>
  User: <b>pi</b>
  <br>
  Password: <b>raspberry</b>
  Change the Password with
  <pre><code>
  passwd
  newpassword
  newpassword
  </code>
  </pre>
    <ol>
    <li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/master/pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz">pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz</a></h4> inludes White- and Blacklist (Advertisement and Maleware)
    with over 70% blocking rate
    </li>
    <li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/master/pi-hole-teleporter_CyberSecurity_Box_without_Porn.tar.gz">pi-hole-teleporter_CyberSecurity_Box_2018-12-20_.tar.gz</a></h4> inludes White- and Blacklist (Advertisement, Maleware and Porn)
    with over 70% blocking rate
    </li><li>
    <h4>The <a href="https://github.com/CyberAndi/CyberSecurity-Box/blob/master/regex.list">regex.list</a></h4> includes Blacklist (Advertisment, Maleware and Porn) with over 40% blocking rate<br>
    
    <pre><code>sudo su
    service pihole stop
    curl -sSL --compressed https://github.com/CyberAndi/CyberSecurity-Box/raw/master/regex.list > regex.list
    cp regex.list /etc/pihole/regex.list
    service pihole start
    </code></pre>
    </li>
  </ol>
</li></ol>
For more Information in german visit https://www.cyberandi.de/Smarthome
</p><P>

contact: <br>
andreas@stawimedia.de<br>
https://www.cyberandi.de
</p>
