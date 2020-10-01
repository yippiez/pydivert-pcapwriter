# pydiver pcapwriter
* This is a basic class that wraps PcapWriter to convert pydivert packet to scapy packet in order to write it into a pcap file.

## Usage:
```
from pydivertwriter import PydivertWriter
import pydivert

pcap_file = PydivertWriter("log.pcap", append = True, sync = True)

with pydivert.Windivert() as w:
  for packet in w:
    pcap_file.write(packet)
    w.send(packet)
``` 
