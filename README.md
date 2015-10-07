# ecg_extract_call

Extract VoIP (SIP) Call Signaling and Corresponding RTP

* Author: Mark R Lindsey, lindsey@e-c-group.com
* Version: 2

# Usage:

```
ecg_extract_call options inputfiles...
```

This extract SIP signaling, then extracts RTP that appears to be related to the SDP found in that signaling.

"inputfiles" are the set of PCAP files that may contain this call. They are scanned twice: once for finding the signaling, then a second time for extrdacting the RTP.

# Options:

`-R` Select source signaling packets using this read (display) filter

`-w` Write the captured data to an output PCAP file. By default, PCAP output is written to standard output.

`-a` Concatenate, rather than merge, the input files.

# Example:

```
/usr/local/bin/ecg_extract_call -R 'sip contains 5146885111' -w calls_with_nick.pcap *.pcap
```
