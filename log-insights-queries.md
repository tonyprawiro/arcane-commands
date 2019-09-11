# VPC Flow Logs

## Query01: TCP inbound traffic to a specific instance

Get all traffic going to a specific instance. Show only accepted TCP traffic, those not filtered by NACL/Security Groups. Sorted by dstPort ASC to ensure that ephemeral ports (response packets) are placed after commonly-used ports.

```
fields @timestamp, protocol, srcAddr, srcPort, dstAddr, dstPort
| filter action='ACCEPT' and protocol=6 and dstAddr='172.31.45.31'
| sort dstPort
```

