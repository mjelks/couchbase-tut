# couchbase-tut
Couchbase Day Tutorial

## Setup
1. Download [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [VirtualBox Extensions](https://www.virtualbox.org/wiki/Downloads)
2. Download [Couchbase OVA File](https://s3-us-west-1.amazonaws.com/couchbaseday/cbday-setup/cbday-4.5-sandbox.ova
) ([Troubleshooting Guide](https://s3-us-west-1.amazonaws.com/couchbaseday/cbday-setup/Troubleshooting%20Guide%20-%20Couchbase%20Day%20Labs.docx
))
3. Copy the appliance .ova file to your local drive
4. Turn off all VPN
5. File -> Import Appliance
6. Two nodes/VMs should appear after import
7. VirtualBox -> Preferences -> Network -> HostOnly Network
	- Doubleclick avail. interface
	- Add Host-Only interface if it doesn't already exist
	- Set Adapter and DHCP server to: 
		- 192.168.61.100 (server address)
		- 255.255.255.0  (server mask)
		- 168.168.61.101 (lower address)
		- 192.168.61.254 (upper address)
8. Fix Host-Only interface Adapetr from vboxnet# to "VirtualBox Host Only Ethernet Adapter"
9. Click OK
10. Verify interface changed to "Virtual Box Host Only Ethernet Adapter"
11. Should now see two enabled interfaces:
	- NAT
	- Host-only Adapter
12. Test Couchbase VMs
	- ssh root@192.168.61.102/101
	- password: couchbase123
	- ps -ef | grep -i couchbase

## URLs 
- [http://192.168.61.101:8091
](http://192.168.61.101:8091
)
- [http://192.168.61.102:8091](http://192.168.61.102:8091)

## Startup
- ssh root@192.168.61.101
- Password: couchbase123
- cd /home/vagrant/try-cb-nodejs; node app.js
- Check via your browser: 
	- [http://192.168.61.101:3000/](http://192.168.61.101:3000/)


