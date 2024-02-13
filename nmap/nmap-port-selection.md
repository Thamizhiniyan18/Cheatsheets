# Nmap Port Selection

| Command                        | Description                                          |
| ------------------------------ | ---------------------------------------------------- |
| `nmap <Target IP>`             | Scan single IP                                       |
| `nmap <Target IP> <Target IP>` | Scan specific IPs                                    |
| `nmap <Target IP range>`       | Scan a range of IPs                                  |
| `nmap <Target Website>`        | Scan a host                                          |
| `nmap <Target Domain>`         | Scan a domain                                        |
| `nmap <Target IP/Subnet>`      | Scan using CIDR notation                             |
| `nmap -iL file.txt`            | Scan targets using given file                        |
| `nmap --exclude <Target IP>`   | Exclude listed host/ specified IPs exclude from scan |
| `nmap -iR 50`                  | Scan 50 random hosts                                 |
