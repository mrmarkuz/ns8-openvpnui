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

## Uninstall

To uninstall the instance:

    remove-module --no-preserve openvpnui1

