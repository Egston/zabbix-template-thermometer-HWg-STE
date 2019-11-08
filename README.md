Zabbix template for ethernet thermometer HWg-STE
================================================

Requirements
------------

Zabbix 4.4


Features
--------

- Low-level discovery for sensors according to SNMPv2.
- Trigger for thermometer Invalid, OutOfRangeLo, OutOfRangeHi, AlarmLo, AlarmHi
  state.
- Graph and screen for sensors values.
- Web scenario and trigger testing whether http://{HOST.IP}/values.xml is
  accessible.
- SNMPv2 item "Device HW MAC address"

This template does not include items already available via "Template SNMP
Generic" like device name, location, uptime etc.

Missing
-------

- Low/High alarm thresholds and hysteresis. These are exported in
  values.xml but not SNMP. However you can test if sensor is in AlarmLo/AlarmHi
  state.

HWg-STE troubleshooting
-----------------------

HWg-STE thermometers seem to have problem with SNMP bulk requests;
you probable need to disable "Use bulk requests" for SNMP interfaces in
host configuration.

They also sometime stops to respond to Zabbix proxy if within the same
broadcast domain.

Possible workarounds:

- Start pinging the thermometer from the Zabbix server/proxy and while
pinging restart the sensor.

- Use a Zabbix proxy outside the broadcast domain.

