# openvpn-proxy
Docker Alpine OpenVPN Privoxy

```Shell
docker run -d \
--cap-add=NET_ADMIN \
--device=/dev/net/tun \
--name=office \
--dns=1.1.1.1 --dns=9.9.9.9 \
--restart=always \
-e "OVPNPATH=<relative/path/to/my.opvn>" \
-e "USERNAME=<vpn_username>" \
-e "PASSWORD=<vpn_password>" \
-e "LOCAL_NETWORK=192.168.1.0/24" \
-e "UID=1000" \
-e "GID=1000" \
-v /etc/localtime:/etc/localtime:ro \
-v </host/path/to/config/data>:/config \
-p 8118:8118 \
act28/openvpn-proxy
