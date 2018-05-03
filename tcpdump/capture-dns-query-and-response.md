# Capture DNS queries and responses.

To capture the packets of DNS queries and reponses, You can use `tcpdump` whth simple filters.

Sample

```zsh
sudo tcpdump -i eth0 -n -vvvv dst port 53 or src port 53
```

`eth0`, the interface name might differ for each environment.

The last `dst port 53 or src port 53` is the filter expression part detail of which can read at `man pcap-filter` 

`-vvvv` indicates the level of verbosity. Not sure its range...

`-n` option prevents from showing the DNS name of each IP address included in the log. 
This feature is useful in many cases but in this case, when we want to capture DNS query packets, 
it might generate misleading packets.

## Learn more

see man page

```zsh
man tcpdump
man pcap-filter
```

