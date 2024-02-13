# Nmap Port Scan Types

| Command                                                                       | Description                                                            |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `nmap -sT <Target IP>`                                                        | Connect Scan (Default without root privileges)/ Scan using TCP connect |
| `nmap -sS <Target IP>`                                                        | Scan using TCP SYN scan (default)                                      |
| `nmap -Su <Target IP>`                                                        | UDP Scan                                                               |
| `nmap -sA <Target IP>`                                                        | ACK Scan                                                               |
| `nmap -Sw <Target IP>`                                                        | Window Scan                                                            |
| `nmap -sM <Target IP>`                                                        | Maimon Scan                                                            |
| `nmap -sL <Target IP>`                                                        | No Scan, list targets only                                             |
| `nmap -sL -v <Target IP>`                                                     | List scan                                                              |
| `nmap -Pn <Target IP>`                                                        | Disable host discovery, port scanning                                  |
| `nmap -PSx <Target IP>`                                                       | SYN Discovery on port x, port 80 by default                            |
| `nmap -PUx <Target IP>`                                                       | UDP discovery on port x, port 40125 by default                         |
| `nmap -PAx <Target IP>`                                                       | ACK discovery on port x, port 80 by default                            |
| `nmap -PR <Target IP>/24`                                                     | ARP discovery on local network                                         |
| `nmap -n <Target IP>`                                                         | Never do DNS resolution                                                |
| `nmap -p x <Target IP>`                                                       | Scan for port x                                                        |
| `nmap -p 21-50 <Target IP>`                                                   | Port Range                                                             |
| `nmap -p U:53,T:21-25,80`                                                     | Scan multiple TCP and UDP ports                                        |
| `nmap -p- <Target IP>`                                                        | Scan all ports                                                         |
| `nmap -p http,ftp <Target IP>`                                                | Port scan from service name                                            |
| `nmap -F <Target IP>`                                                         | Fast port scan (100 ports)                                             |
| `nmap -f <Target IP>`                                                         | Scan fragmented IP packets                                             |
| `nmap --mtu x <Target IP>`                                                    | Set own offset size x                                                  |
| `nmap --top-ports x <Target IP>`                                              | Scan the top x ports                                                   |
| `nmap -sV --version-intensity 5 <Target IP>`                                  | Aggressive service discovery                                           |
| `nmap -sV -–version-intensity 0 <Target IP>`                                  | Light banner grabbing                                                  |
| `nmap -sV--version-light <Target IP>`                                         | Enable light mode, lower possibility of correctness                    |
| `nmap -sV--version-all <Target IP>`                                           | Enable intensity level 9. Higher possibility of correctness            |
| `nmap -O--osscan-limit <Target IP>`                                           | Limit OS detection to promising targets                                |
| `nmap -O--osscan-guess <Target IP>`                                           | Guess OS detection results                                             |
| `nmap -O --max-os-tries x <Target IP>`                                        | Set maximum number of OS detection tries against a target              |
| `nmap -sU -p 123,161,162 <Target IP>`                                         | Scan UDP ports                                                         |
| `nmap -Pn -F <Target IP>`                                                     | Scan selected ports - ignore discovery                                 |
| `nmap -Pn -sT --scan-delay 1s --max-parallelism 1 -p <Port List> <Target IP>` | Identify open ports and services                                       |
| `nmap -Pn -sT -p 46824 <Target IP>`                                           | Identify HMI systems                                                   |
| `nmap -Pn -sT -p 102 --script s7-info <Target IP>`                            | Scan Siemens SIMATIC S7 PLCs                                           |
| `nmap -Pn -sT -p 502 --script modbus-discover <Target IP>`                    | Scan Modbus Devices                                                    |
| `nmap -sU -p 500 <Target IP>`                                                 | Check the status of isakmp over port 500                               |
| `nmap -Pn -sU -p 47808 --script bacnet-info <Target IP>`                      | ScanBACnet Devices                                                     |
| `nmap -Pn -sU -p 44818 --script enip-info <Target IP>`                        | Scan Ethernet/IP Devices                                               |
| `nmap -Pn -sT -p 1911,4911 --script fox-info <Target IP>`                     | Scan Niagara Fox Devices                                               |
| `nmap -Pn -sT -p 20547 --script proconos-info <Target IP>`                    | Scan ProConOS Devices                                                  |
| `nmap -Pn -sT -p 9600 --script omron-info <Target IP>`                        | Scan Omron PLC Devices                                                 |
| `nmap -Pn -sT -p 1962 --script pcworx-info <Target IP>`                       | Scan PCWorx Devices                                                    |
