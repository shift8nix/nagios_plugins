# nagios_plugins

My Nagios Plugins

## check_ros_version

Check Mikrotik RouterOS version using snmp.

In basic form perform only check response. Response:

```
OK: RouterOS 6.34.6 (bugfix) on CRS125-24G-1S | 6.34
```
If used with --track option compare with latest version using https://lsrel.com. Response:
```
CURRENT: RouterOS 6.34.6 (bugfix) on CRS125-24G-1S | 6.34
```
Error looks like this:
```
NOT CURRENT: NEW="6.36(current)" RouterOS 6.34.6 (bugfix) on CRS125-24G-1S | 6.34
```
## check_port_status

Check network interface status using snmp.

Performs checks for both administrative and operational state in same service. 

Tested so far on Cisco, Mikrotik and Linux x86.

In basic form return only current states. Response:
```
OK: Int:8   State:UP UP |  admin=1 oper=1
```
Optionally return interface description and/or type. Response:
```
OK: Int:8 T:ethernetCsmacd D:ether8 State:UP UP |  admin=1 oper=1
```
Error looks like this:
```
OPER CHANGE: Int:9   State:UP DOWN Desired:UP UP |  admin=1 oper=0
```
Other options include: ignore operational state changes - useful for wifi or vpn interfaces.

Set desired oper or admin state as down - useful for dissabled or unconnected links.
