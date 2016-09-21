# lesson11

<h3>Settings for node:</h3>
/etc/sysconfig/network => hostname = node1.mihura.com
<br>/etc/hosts/            => 192.168.33.14 master.mihura.com master

<h3>Settings for master:</h3>
/etc/sysconfig/network => hostname = master.mihura.com
<br>/etc/hosts/            => 192.168.33.13 node1.mihura.com node1

<b>Installed puppet and puppetserver for node, master
<br>We can add "server = master.mihura.com" to /etc/puppetlabs/puppet/puppet.conf on node for use next command without '--server'
<br>Then use next commands:</b>
* on node: puppet agent -t --server master.mihura.com --waitforcert 60 --test
* on master: Puppet cert --sign node1.mihura.com
