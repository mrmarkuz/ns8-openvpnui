# ns8-openvpnui

[OpenVPN UI](https://github.com/d3vilh/openvpn-ui) is a OpenVPN server web administration interface. OpenVPN Server is included.

## Install

Instantiate the module with:

    add-module ghcr.io/nethserver/openvpnui:latest 1

The output of the command will return the instance name.
Output example:

    {"module_id": "openvpnui1", "image_name": "openvpnui", "image_url": "ghcr.io/nethserver/openvpnui:latest"}

## Configure

Configure the FQDN and browse to it. Login with username admin and password Nethesis,1234

In the profile configuration of the Administrator on top right, set a mail address and a new password

In OpenVPN UI settings, set the Management interface to `10.0.70.1:2080`

In the OpenVPN Server configuration set DNS servers and subnets

In the OpenVPN Client configuration set the connection address to the openvpnui FQDN

Create a certificate on the certificate page

Click on the certificate name to download the client .ovpn file

Import the file on a client and connect

To block access to the wireguard IP you could add the following to `state/fw-rules.sh`:

```
iptables -A FORWARD -s 10.0.70.0/24 -d 10.5.4.1 -j DROP
iptables -A FORWARD -d 10.5.4.1 -s 10.0.70.0/24 -j DROP
```

Check the [documentation](https://github.com/d3vilh/openvpn-ui?tab=readme-ov-file#firewall-rules) for an example to isolate clients from each other.

## Uninstall

To uninstall the instance:

    remove-module --no-preserve openvpnui1

