The usage is:
# ls
openvpn-ipset.fc openvpn-ipset.te
# make -f /usr/share/selinux/devel/Makefile
...
# ls
openvpn-ipset.fc  openvpn-ipset.if  openvpn-ipset.pp  openvpn-ipset.te
# restorecon -Frv /usr/sbin/ipset
...
# semodule -i openvpn-ipset.pp

You can add rules from audit2allow output to the module and repeat
the steps above to further adjust the policy.

To remove the policy module:
# semodule -r openvpn-ipset
