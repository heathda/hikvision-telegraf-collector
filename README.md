# hikvision-telegraf-collector
Hikvision IP Camera Telegraf SNMP Collector

## Statistics Collected
- Manufacturer
- Device Model
- CPU Percentage
- Memory Percentage
- Static IP
- Video Encoding

"HIK-DEVICE-MIB::cpuPercent.0" and "HIK-DEVICE-MIB::memUsed.0" return values in a non-integer format.  
Example: "10 PERCENT" (without the quotes).

Regex and converter plugins are used to remove " PERCENT" and change the results into integers for easy graphing.

## HIK-DEVICE-MIB

HIK-DEVICE-MIB.txt does include additional information that may be useful to your monitoring needs.  hikvision.conf only includes the statistics listed above.

HIK-DEVICE-MIB.txt will need to be added to the location your system keeps it's MIB files.
- /usr/share/snmp/mibs on Ubuntu 20.04.1 LTS

The following information is available and can be tested with snmpwalk  
Run the following command with your community password and ip address
- snmpwalk -v 2c -c public 192.168.1.100 .1.3.6.1.4.1.39165

HIK-DEVICE-MIB::deviceType.0 = STRING: "DS-2CDXXXXXX"  
HIK-DEVICE-MIB::hardwVersion.0 = STRING: "0"  
HIK-DEVICE-MIB::softwVersion.0 = STRING: "VX.X.X build XXXXXX"  
HIK-DEVICE-MIB::macAddr.0 = STRING: "aa-bb-cc-11-22-33"  
HIK-DEVICE-MIB::deviceID.0 = STRING: "00"  
HIK-DEVICE-MIB::manufacturer.0 = STRING: "Hikvision"  
HIK-DEVICE-MIB::cpuPercent.0 = STRING: "11 PERCENT"  
HIK-DEVICE-MIB::diskSize.0 = STRING: "0.0 GB"  
HIK-DEVICE-MIB::diskPercent.0 = STRING: "0 PERCENT"  
HIK-DEVICE-MIB::memSize.0 = STRING: "256 MB"  
HIK-DEVICE-MIB::memUsed.0 = STRING: "79 PERCENT"  
HIK-DEVICE-MIB::restartDev.0 = INTEGER: 0  
HIK-DEVICE-MIB::dynIpAddr.0 = IpAddress: 0.0.0.0  
HIK-DEVICE-MIB::dynNetMask.0 = IpAddress: 0.0.0.0  
HIK-DEVICE-MIB::dynGateway.0 = IpAddress: 0.0.0.0  
HIK-DEVICE-MIB::staticIpAddr.0 = IpAddress: 192.168.1.100  
HIK-DEVICE-MIB::staticNetMask.0 = IpAddress: 255.255.255.0  
HIK-DEVICE-MIB::staticGateway.0 = IpAddress: 192.168.1.1  
HIK-DEVICE-MIB::sysTime.0 = STRING: "YYYY-MM-DD HH:MM:SS"  
HIK-DEVICE-MIB::videoInChanNum.0 = INTEGER: 1  
HIK-DEVICE-MIB::videoEncode.0 = STRING: "H.264"  
HIK-DEVICE-MIB::videoNetTrans.0 = STRING: "H.264"  
HIK-DEVICE-MIB::audioAbility.0 = INTEGER: 0  
HIK-DEVICE-MIB::audioInNum.0 = INTEGER: 0  
HIK-DEVICE-MIB::videoOutNum.0 = INTEGER: 0  
HIK-DEVICE-MIB::clarityChanNum.0 = INTEGER: 1  
HIK-DEVICE-MIB::localStorage.0 = INTEGER: 1  
HIK-DEVICE-MIB::rtspPlayBack.0 = INTEGER: 1  
HIK-DEVICE-MIB::netAccessType.0 = STRING: "ETHERNET"  
HIK-DEVICE-MIB::alarmInChanNum.0 = INTEGER: 0  
HIK-DEVICE-MIB::alarmOutChanNum.0 = INTEGER: 0  
HIK-DEVICE-MIB::manageServAddr.0 = IpAddress: 0.0.0.0  
HIK-DEVICE-MIB::ntpServIpAddr.0 = STRING: "ntp-b.nist.gov"  
HIK-DEVICE-MIB::managePort.0 = INTEGER: 0  
