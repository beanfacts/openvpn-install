# openvpn-install

OpenVPN installer for Debian, Ubuntu, Fedora, CentOS and Arch Linux.

This script will let you setup your own secure VPN server in just a few seconds.  
**This fork adds 1:1 NAT functionality.**

## Usage

The intended usage for this fork is that you either want a public static IPv4 address or port forwarding.  
Just spin up a VPS with Ubuntu 18.04+ (this is all I tested the 1:1 NAT feature with) and a public IPv4 address.  
Run the following **as root**:

```bash
curl -O https://raw.githubusercontent.com/beanfacts/openvpn-install/master/openvpn-install.sh
chmod +x openvpn-install.sh
./openvpn-install.sh
```

After running the install script, run it again and select the 1:1 NAT option.  
This should forward all ports except those in use (for example, it may not forward SSH).  
If you want it to assign you a static IP address automatically please install `ipcalc`.
When you run it on a fresh install the forwarding rule additions **should** be automatic.

```sh
./openvpn-install.sh
```

You need to run the script as root and have the TUN module enabled.
In your home directory, you will have `.ovpn` files. These are the client configuration files. Download them from your server and connect using your favorite OpenVPN client.

**If you're using 1:1 NAT you should only have a single user configured!**

## Questions not involving the 1:1 NAT part
Dunno. I barely know how to use Bash.

## Credits & Licence

Many thanks to the [upstream fork contributors](https://github.com/Angristan/OpenVPN-install/graphs/contributors) and Nyr's original work.

This project is under the [MIT Licence](https://raw.githubusercontent.com/beanfacts/openvpn-install/master/LICENSE)
