# Nmap Options

## Target Specification

| Option ( Switch / Syntax )              | Description                                                  |
| --------------------------------------- | ------------------------------------------------------------ |
| `-iL <inputfilename>`                   | Input from list of hosts/networks                            |
| `-iR <num hosts>`                       | Choose random targets/ Scan random hosts `nmap -iR [number]` |
| `--exclude <host1[,host2][,host3],...>` | Exclude single or multiple hosts/networks                    |
| `--excludefile <exclude_file>`          | Exclude list from file                                       |

## Host Discovery

| Option ( Switch / Syntax )          | Description                                                                                              |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `-sL`                               | List Scan - simply lists targets `nmap <Target IP>-3 -sL`                                                |
| `-sn`                               | Ping Scan - disable port scan for discovering host `nmap <Target IP>/24 -sn`                             |
| `-Pn`                               | Treat all hosts as online -- skip host discovery nmap `<Target IP>-5 -Pn`                                |
| `-PS/PA/PU/PY[portlist]`            | TCP SYN/ACK, UDP or SCTP INIT discovery to given ports                                                   |
| `-PE/PP/PM`                         | ICMP echo, timestamp, and netmask request discovery probes                                               |
| `-PP`                               | Use ICMP timestamp request                                                                               |
| `-PO[protocol list]`                | IP Protocol Ping                                                                                         |
| `-n/-R`                             | Never do DNS resolution/Always resolve \[default: sometimes] `nmap –n <Target IP>` `nmap –R <Target IP>` |
| `--dns-servers <serv1[,serv2],...>` | Immediate mode, display things as we find them                                                           |
| `--system-dns`                      | A string representing the intended sequence ignorance level                                              |
| `--traceroute`                      | Path to a file where flat text will be dumped that normally would go to the users terminal               |
| `-PR`                               | Numeric value representing the number of seconds to wait before declaring the scan over                  |

## Scan Techniques

| Option ( Switch / Syntax )      | Description                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------- |
| `-sS/sT/sA/sW/sM`               | TCP SYN/Connect()/ACK/Window/Maimon scans                                                |
| `-sU`                           | UDP Scan `nmap -sU -v <Target IP>` UDP port scan `nmap <Target IP> -sU`                  |
| `-sN/sF/sX`                     | TCP Null, FIN, and Xmas scans                                                            |
| `--scanflags=value –sA`         | TCP ACK scan `nmap --scanflags=value –sA <Target IP>`                                    |
| `-–scanflags`                   | TCP scan flags `nmap --scanflags <Target IP>`                                            |
| `-Sp`                           | Ping scan `nmap -Sp <Target IP>`                                                         |
| `--scanflags <flags>`           | Customize TCP scan flags                                                                 |
| `-sI <zombie host[:probeport]>` | Idle zombie scan `nmap –sI zombie <Target IP>`                                           |
| `-sY/sZ`                        | SCTP INIT scan `nmap -sY -v <Target IP>` SCTP COOKIE-ECHO scan `nmap -sZ -v <Target IP>` |
| `-sO`                           | IP protocol scan `nmap –sO <Target IP>`                                                  |
| `-b <FTP relay host>`           | FTP bounce scan                                                                          |
| `–send-eth`                     | Send raw ethernet packets `nmap –send-eth <Target IP>`                                   |
| `–send-ip`                      | Send IP packets `nmap –send-ip <Target IP>`                                              |

## Port Specification and Scan Order

| Option ( Switch / Syntax ) | Description                                                                                                                                                                                |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `-p <port ranges>`         | Only scan specified range ports `nmap -p 1-100 <Target IP>` e.g. -p 80,443 or -p 1–65535                                                                                                   |
| `-p-`                      | Port scans all 1-65535 ports `nmap <Target IP> -p-`                                                                                                                                        |
| `-p <protocol>`            | Port scan from specified protocols `nmap -p smtp,https <Target IP>`                                                                                                                        |
| `-F`                       | Fast mode - Scan less ports than the default scan (scan 100 most common ports) `nmap <Target IP> -F`                                                                                       |
| `-r`                       | Scan ports consecutively – do not randomize                                                                                                                                                |
| `–randomize-hosts`         | Randomize target host order `nmap --randomize-hosts <Target IP>`                                                                                                                           |
| `-p <port1>,<port2>,...`   | Port list                                                                                                                                                                                  |
| `-p <port1>-<port2>`       | Port range                                                                                                                                                                                 |
| `-P "*"`                   | Scan port using name `nmap -p "*" ftp <Target IP>`                                                                                                                                         |
| `-p U:53,U:110,T20-445`    | Mix TCP and UDP                                                                                                                                                                            |
| `--top-ports <number>`     | Scan most common ports                                                                                                                                                                     |
| `--port-ratio <ratio>`     | Scan ports more common than                                                                                                                                                                |
| `-p-65535`                 | Leaving off initial port in range makes Nmap scan start at port 1 `nmap <Target IP> -p-65535` Leaving off initial port in range makes the scan start at port 1 `nmap -p-65535 <Target IP>` |
| `-p0-`                     | Leaving off end port in range makes Nmap scan through port 65535 `nmap <Target IP> -p0-` `nmap -p0- <Target IP>`                                                                           |

## Service / Version Detection

| Option ( Switch / Syntax )    | Description                                                               |
| ----------------------------- | ------------------------------------------------------------------------- |
| `-sV`                         | Probe open ports to determine service/version info `nmap <Target IP> -sV` |
| `--version-intensity <level>` | Set from 0 (light) to 9 (try all probes)                                  |
| `--version-light`             | Limit to most likely probes (intensity 2)                                 |
| `--version-all`               | Try every single probe (intensity 9)                                      |
| `--version-trace`             | Show detailed version scan activity (for debugging)                       |

## Script Scan

| Option ( Switch / Syntax )                                            | Description                                                                 |
| --------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `--script=<ScriptName> ( or ) <ScriptCategory> ( or ) <ScriptDir>...` | Run individual or group of scripts                                          |
| `--script=<Lua scripts>`                                              | is a comma separated list of directories, script-files or script-categories |
| `--script-trace`                                                      | Show all data sent and received                                             |
| `--script-updatedb`                                                   | Update the script database. `nmap --script-updatedb`                        |
| `--script-help`                                                       | “Lua scripts” = Show help about scripts                                     |

## OS Detection

| Option ( Switch / Syntax ) | Description                                                                                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `-O`                       | Enable OS detection/ OS Discovery using Nmap and Unicornscan/ Remote OS Detection using TCP/IP stack fingerprinting `nmap -O <Target IP>` |
| `--osscan-limit`           | Limit OS detection to promising targets                                                                                                   |
| `--osscan-guess`           | Guess OS more aggressively                                                                                                                |
| `--max-os-tries`           | Set the maximum number x of OS detection tries against a target                                                                           |

## Timing and Performance

| Option ( Switch / Syntax )                                      | Description                                                                 |
| --------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `-T<0-5>`                                                       | Set timing template (higher is faster)                                      |
| `–ttl [time]`                                                   | Set the packet TTL `nmap –ttl [time] <Target IP>` `nmap <Target IP>/24 -sn` |
| `--min-hostgroup/max-hostgroup <size>`                          | Parallel host scan group sizes                                              |
| `--min-parallelism/max-paralleli sm <numprobes>`                | Probe parallelization                                                       |
| `--min-rtt-timeout/max-rtt-timeo ut/initial-rtt-timeout <time>` | Specifies probe round trip time                                             |
| `--max-retries <tries>`                                         | Caps number of port scan probe retransmissions                              |
| `--host-timeout <time>`                                         | Give up on target after this long                                           |
| `--scan-delay/--max-scan-delay <time>`                          | Adjust delay between probes                                                 |
| `--min-rate <number>`                                           | Send packets no slower than per second                                      |
| `--max-rate <number>`                                           | Send packets no faster than per second                                      |
| `–defeat-rst-ratelimit`                                         | Defeat reset rate limits `nmap –defeat-rst-ratelimit <Target IP>`           |

## Firewall / IDS Evasion and Spoofing

| Option ( Switch / Syntax )                     | Description                                                                    |
| ---------------------------------------------- | ------------------------------------------------------------------------------ |
| `-f; --mtu <val>`                              | Fragment packets (optionally w/given MTU)                                      |
| `-D <decoy1,decoy2[,ME],...>`                  | Cloak a scan with decoys                                                       |
| `-S <IP_Address>`                              | Spoof source address                                                           |
| `-e <iface>`                                   | Use given port number                                                          |
| `-g/--source-port <portnum>`                   | Append random data to send packets `nmap --data-length [size] <Target IP>`     |
| `--data-length <num>`                          | Send packets with specified IP options                                         |
| `--ip-options <options>`                       | Set IP time-to-live field                                                      |
| `--ttl <val>`                                  | Spoof your MAC address `nmap --spoof-mac [MAC (or) 0 (or) vendor] <Target IP>` |
| `--spoof-mac <mac address/prefix/vendor name>` | Idle zombie scan `nmap --sI zombie <Target IP>`                                |
| `--badsum`                                     | Send packets with a bogus TCP/UDP/SCTP checksum                                |
| `--proxies url1,[url2],...`                    | Relay connections through HTTP/SOCKS4 proxies                                  |

## Output

| Option ( Switch / Syntax ) | Description                                                                                          |
| -------------------------- | ---------------------------------------------------------------------------------------------------- |
| `-oN/-oX/-oS/-oG <file>`   | Output scan in normal, XML, s\<rIpt kIddi3, and Grepable format, respectively, to the given filename |
| `-oA <basename>`           | Output in the three major formats at once                                                            |
| `-v`                       | Increase verbosity level (use -vv or more for greater effect) `nmap -v <Target IP>`                  |
| `-d`                       | Increase debugging level (use -dd or more for greater effect) `nmap -d <Target IPs>`                 |
| `--reason`                 | Display the reason a port is in a particular state                                                   |
| `--open`                   | Only show open (or possibly open) ports `nmap --open <Target IP>`                                    |
| `--packet-trace`           | Show all packets sent and received `nmap --packet-trace <Target IP>`                                 |
| `--iflist`                 | Print host interfaces and routes (for debugging) `nmap --iflist`                                     |
| `--log-errors`             | Log errors/warnings to the normal-format output file                                                 |
| `--append-output`          | Append to rather than clobber specified output files                                                 |
| `--resume <filename>`      | Resume an aborted scan                                                                               |
| `--stylesheet <path/URL>`  | XSL stylesheet to transform XML output to HTML                                                       |
| `--webxml`                 | Reference stylesheet from http://nmap.org/ for more portable XML                                     |
| `--no-stylesheet`          | revent associating of XSL stylesheet w/XML output                                                    |
| `–stats-every [time]`      | Periodically display statistics `nmap –stats-every [time] <Target IP>`                               |

## Miscellaneous Options

| Option ( Switch / Syntax ) | Description                                                                                                                                                                                              |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-h`                       | Nmap help screen `nmap -h`                                                                                                                                                                               |
| `-6`                       | IPv6 Scanning by using -6 option in Zenmap `nmap -6 http://scanme.nmap.org/` Enable IPv6 scanning `nmap -6 2607:f0d0:1002:51::4`. OS discovery using IPv6 fingerprinting method `nmap -6 -O <Target IP>` |
| `-A`                       | Enables OS detection, version detection, script scanning, and traceroute, also known as Aggressive scan                                                                                                  |
| `-n`                       | Disable reverse IP address lookups                                                                                                                                                                       |
| `--datadir <dirname>`      | Specify custom Nmap data file location                                                                                                                                                                   |
| `--send-eth/--send-ip`     | Send using raw ethernet frames or IP packets                                                                                                                                                             |
| `--privileged`             | Assume that the user is fully privileged                                                                                                                                                                 |
| `-V`                       | Display Nmap version `nmap -V`                                                                                                                                                                           |
| `--unprivileged`           | Assume the user lacks raw socket privileges                                                                                                                                                              |
