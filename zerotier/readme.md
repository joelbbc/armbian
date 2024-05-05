FIREWALL FORWARDING
-  Enable IP forwarding : sudo sysctl -w net.ipv4.ip_forward=1
-  Configure iptables : PHY_IFACE=eth0; ZT_IFACE=ztmjfkb3mw   #ZT_IFACE=ztmjfkb3mw YOUR ZT Interface
-  Add rules to iptables :   -  sudo iptables -t nat -A POSTROUTING -o $PHY_IFACE -j MASQUERADE
                              -  sudo iptables -A FORWARD -i $PHY_IFACE -o $ZT_IFACE -m state --state RELATED,ESTABLISHED -j ACCEPT
                              -  sudo iptables -A FORWARD -i $ZT_IFACE -o $PHY_IFACE -j ACCEPT
-  Simpan iptables agar berjalan ketika reboot: -  sudo apt install iptables-persistent
                                                -  sudo bash -c iptables-save > /etc/iptables/rules.v4

Referensi : https://n-tekno.web.id/stb-armbian-linux-sebagai-remote-server-zerotier/
