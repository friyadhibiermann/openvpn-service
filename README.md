# openvpn-service
unix/linux openwrt cronjob every 6 hours
<h2>menginstallasi program<h2>
<h3>menyimpan file</h3>
<code>
git clone https://github.com/friyadhibiermann/openvpn-service
</code>
<h3>membuat symlink</h3>
<code>
ln -s $PWD/openvpn-service /usr/bin/openvpn-service
</code>
<h3>menyimpan file konfigurasi</h3>
<code>
file=$(find - L $PWD/ -type f \( -iname \*.ovpn -o -iname \*.conf -iname \*.txt \));for i in $file;do mv $i /etc/openvpn/;done
</code>
<h3>test script<h3>
<code>
openvpn-service
</code>
<h2>mengatur crontab<h2>
<h3>schredule run program 1 time every 6 hours<h3>
<code>
crontab -e
</code>
<code>
0 */6 * * * openvpn-service
</code>
