# VPC Flow Logs

## Query01: TCP traffic to a specific instance

```
fields @timestamp, protocol, srcAddr, srcPort, dstAddr, dstPort
| filter action='ACCEPT' and protocol=6 and dstAddr='172.31.45.31'
| sort bytesTransferred desc
```

