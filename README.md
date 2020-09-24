# hikvision-telegra-collector
Hikvision IP Camera Telegraf SNMP Collector

## Statistics Collected
- Manufacturer
- Device Model
- CPU Percentage
- Memory Percentage
- Static IP
- Video Encoding

HIK-DEVICE-MIB::cpuPercent.0 and HIK-DEVICE-MIB::memUsed.0 return values in a non-integer format.  Example: "10 PERCENT" (without the quotes).

Regex and converter plugins are used to remove " PERCENT" and change the results into integers for easy graphing.
