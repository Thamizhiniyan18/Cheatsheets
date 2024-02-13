# NSE Scripts

## Syntax

| Command                                                                     | Description                       |
| --------------------------------------------------------------------------- | --------------------------------- |
| `nmap -sC <Target IP>`                                                      | Scan with default NSE scripts     |
| `nmap --script-default <Target IP>`                                         | Scan with default NSE scripts     |
| `nmap --script snmp-sysdescr --script-args snmpcommunity=admin <Target IP>` | NSE script with arguments         |
| `nmap -script-args-file=filename`                                           | Provide NSE script args in a file |
| `nmap -sV -sC <Target IP>`                                                  | Scan using default safe scripts   |
| `nmap -sV --script=smb* <Target IP>`                                        | Scan with a set of scripts        |
| `nmap -sV -p 443 –script=ssl-heartbleed.nse <Target IP>`                    | Scan using a specific NSE script  |

***

## NetBios - 137, 138, 139

| Command                                            | Description                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| `nmap -sV -v --script nbtstat.nse <Target IP>`     | Attempts to retrieve the target's NetBIOS names and MAC address |
| `nmap -sU -p 137 --script nbtstat.nse <Target IP>` | Attempts to retrieve the target's NetBIOS names and MAC address |

***

## SMB - 139, 445

| Command                                                                                                                | Description                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sudo nmap --script smb-os-discovery.nse <Target IP>`                                                                  | Attempts to determine the operating system, computer name, domain, workgroup, and current time over the SMB protocol                                                                          |
| `nmap --script smb-enum-shares.nse -p445 <Target IP>`                                                                  | Attempts to list shares using the srvsvc.NetShareEnumAll MSRPC function and retrieve more information about them using srvsvc.NetShareGetInfo                                                 |
| `nmap --script smb-enum-users.nse -p445 <Target IP>`                                                                   | Attempts to enumerate the users on a remote Windows system, with as much information as possible, through two different techniques (both over MSRPC, which uses port 445 or 139; see smb.lua) |
| `nmap -sU -p 445 --script=smb-enum-groups <Target IP>`                                                                 | Obtains a list of groups from the remote Windows system, as well as a list of the group's users                                                                                               |
| `nmap --script smb-enum-services.nse -p445 <Target IP>`                                                                | Retrieves the list of services running on a remote Windows system                                                                                                                             |
| `nmap -sU -p 445 --script=smb-enum-services --script-args smbusername=administrator,smbpassword=smbserver_77 <target>` | Retrieves the list of services running on a remote Windows system                                                                                                                             |

***

## SNMP - 161, 162, 10161, 10162

| Command                                             | Description                                           |
| --------------------------------------------------- | ----------------------------------------------------- |
| `nmap -sU -p 161 --script=snmp-processes <target>`  | Attempts to enumerate running processes through SNMP  |
| `nmap -sU -p 161 --script=snmp-interfaces <target>` | Attempts to enumerate network interfaces through SNMP |
