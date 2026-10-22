# Basic AD DNS overview and useful troubleshooting commands

Here is the list of used commands and what they do:
- `nslookup <IP-or-Domain>` – manually querying DNS server to translate IP to domain name or the other way around
- `ping <IP-or-Domain>` – used to test connectivity
- `dcdiag /v` – used to run DNS diagnostics nad check the health of AD DNS service
- `dcdiag /test:dns /v` – runs deep and specific DNS test in of AD DNS
- `repadmin /replsummary` – shows current DCs
- `repadmin /showrepl` – shows detailed history of replications between DCs.
- `nltest /dclist:<domain-name>` shows list of every DC in domain and which one has PDC role
- `Get-DnsClientServerAddress` – shows which DNS servers are used by the system
- `Resolve-DnsName` – used to show SRV records (kerberos, ldap)

## Testing diagnostics commands

The most basic troubleshooting commands for checking if DNS is responding are `ping` and `nslookup`.

Using `ping <Machine-Host-Name>` in terminal, we can check if DNS can respond with the correct IP address.

<img width="1110" height="622" alt="image" src="https://github.com/user-attachments/assets/6183348e-8dd3-4724-9e16-2729b20cd8e8" />

Similarly using `nslookup <Machine-Host-Name>` in terminal, the command should respond with corresponding IP address for that domain name.

<img width="1107" height="623" alt="image" src="https://github.com/user-attachments/assets/6e6f7e3e-51b4-4607-8b27-d97487492821" />

We can also use `nslookup <Machine-IP-Address>` to get domain name for that ip address.

<img width="1112" height="620" alt="image" src="https://github.com/user-attachments/assets/18df5b8d-3758-4f4f-aa58-9c40fdf23a53" />

## AD DNS Diagnostics

Using `dcdiag /v` command in terminal, we can chceck overall health of DNS services in our domain.

<img width="1714" height="869" alt="image" src="https://github.com/user-attachments/assets/74d95596-f2e6-4a5c-a460-7e8b3bb8149d" />

For a detailed overview of our DNS we can use `dcdiag /test:dns /v` command. This will take few minutes to run.

<img width="1716" height="874" alt="image" src="https://github.com/user-attachments/assets/020178ca-f16b-450f-b9bc-592c6a939d21" />

<img width="1027" height="527" alt="image" src="https://github.com/user-attachments/assets/6bfd5542-fcb5-4bfa-921e-2d0189040b4a" />

To check replication, we can use the `repadmin /replsummary` command.

<img width="1105" height="623" alt="image" src="https://github.com/user-attachments/assets/776b9feb-01b7-4cb7-8b55-d3b39155d7d0" />

To chceck detailed replication history we can use `repandmin /showrepl` command.

<img width="1714" height="866" alt="image" src="https://github.com/user-attachments/assets/06dc4153-6367-4ce4-a3ed-5ea681dda5bf" />

We can get the list of available DCs with `nltest /dclist:<Domain-Name>` command.

<img width="1111" height="621" alt="image" src="https://github.com/user-attachments/assets/953354ba-4ba5-408f-ace0-1bbc1122f1f6" />

Getting list of used DNS servers can be done with `get-dnsclientserveraddress` command.

<img width="1109" height="542" alt="image" src="https://github.com/user-attachments/assets/bad0e17a-1bc7-41f4-8812-a551f5765b01" />

For detailed information about SRV records we can use these 2 commands:
- `resolve-dnsname -Name _ldap._tcp.dc._msdcs.winad.lan -Type SRV`
- `resolve-dnsname -Name _kerberos._tcp.dc._msdcs.winad.lan -Type SRV`

<img width="1111" height="622" alt="image" src="https://github.com/user-attachments/assets/7414bc8e-7849-440e-9b6b-e4cf57bc64b9" />

<img width="1105" height="551" alt="image" src="https://github.com/user-attachments/assets/e6eb7d22-659a-476c-b136-2019f3c5f42b" />
