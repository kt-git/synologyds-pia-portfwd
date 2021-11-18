# synologyds-pia-portfwd
Scripts to configure Synology DownloadStation to use PrivateInternetAccess dynamic forwarded port

Initial commit of the script I use to update Synology DownloadStation to use the dynamically-forwarded ports provided by PrivateInternetAccess VPN.

This script combined excellent prior work from two others:

GamerGun's port_forwarding.sh script: https://gist.github.com/GamerGun/20f08da8ff2712db6e62c5edc83fd541
(This provided a working pattern to parse and update DownloadStation configuration and then stop and start the service)

fm407's PIA-NextGen-PortForwarding script: https://github.com/fm407/PIA-NextGen-PortForwarding/blob/master/pia-nextgen-pf.sh
(This provided a working example of interacting with the PIA API via curl to query for the dynamic forwarded port)

Then I added a basic upstart script so the NAS can run this script on startup.

To Install:

* Copy the pia-diskstation-fwd.sh script into /usr/local/bin/ on the synology nas.
* Copy the pia-portforward.conf script into /etc/init/ on the synology nas.
* Make sure the pia-diskstation-fwd.sh script is executable
* Test the upstart script is working by running "start pia-portfoward"
