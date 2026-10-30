# Configuring DHCP Failover on Windows Server 2025

## Setting up second DHCP server

On your second windows server, install the DHCP Server Role.

After successful installation complete the **DHCP Post-Install configuration wizard**. 

<img width="783" height="557" alt="image" src="https://github.com/user-attachments/assets/c818699f-5732-4e88-b061-6a505797960c" />

<img width="759" height="557" alt="image" src="https://github.com/user-attachments/assets/3d257cfe-a51d-414e-b2b0-32b11f8bfc95" />

---

Switch to your main DHCP Server and open the DHCP settings from **Server Manager**.

In the left menu, right-click on **DHCP** and select *Add Server...* .

<img width="322" height="212" alt="image" src="https://github.com/user-attachments/assets/34d72a30-b201-4882-abb3-112e36cf143f" />

In the **Add Server** window select *Browse...* and enter the name of your second DHCP Server.

Select *OK* and then *OK*.

<img width="896" height="325" alt="image" src="https://github.com/user-attachments/assets/75bebdf6-77e3-41f6-beb7-f0b20ec9db5c" />

The server is now visible in the **DHCP** menu.

<img width="332" height="165" alt="image" src="https://github.com/user-attachments/assets/ae25e615-606a-4e78-850b-0e470863549e" />

## Scope replication and configuring failover

To replicate scope from first DHCP server on to the second DHCP server in **DHCP** menu, go into `<first-DHCP-server> > IPv4`, right click the scope you want to replicate and click *Configure Failover...* .

<img width="528" height="439" alt="image" src="https://github.com/user-attachments/assets/6a825a5d-388e-41ea-94de-9b7059ffedb0" />

Navigate trough **Configure Failover** wizard.

As a partner server, select your second DHCP server.

You can also specify details like Mode (load balance or hot standby), load balance percentage, shared secret and more.

For this lab, use *Hot standby* mode, make sure the partner server is set up as standby, enable switchover interval and disable *Message Authentication*.

<img width="497" height="549" alt="image" src="https://github.com/user-attachments/assets/f165a6b7-6c8a-4ee2-95d8-2f00b990f485" />

<img width="499" height="548" alt="image" src="https://github.com/user-attachments/assets/b736f8e4-73a9-43ce-90aa-69fd98ceeca0" />

<img width="499" height="547" alt="image" src="https://github.com/user-attachments/assets/44179cdd-f699-420d-b70f-4c16b62a088f" />

<img width="495" height="546" alt="image" src="https://github.com/user-attachments/assets/7b5100ff-df09-4824-a186-7f24fe9c3e5f" />

<img width="420" height="355" alt="image" src="https://github.com/user-attachments/assets/ebdd1819-02d0-47ae-8a3b-9bd3a4cb4a5c" />

---

After failover configuration, both servers will have the same scope.

<img width="489" height="461" alt="image" src="https://github.com/user-attachments/assets/8dc9604c-74dc-4956-ba1c-b67c03fdf768" />

## Validating DHCP failover configuration

Once DHCP failover is set up, switch to your windows 11 client.

Open Terminal and type `ipconfig /release` and then `ipconfig /renew`. This process will request a new address from your DHCP server.

<img width="1109" height="624" alt="image" src="https://github.com/user-attachments/assets/3d7b75ab-c7a0-4196-bd4c-92df611718a2" />

Check your IP configuration and look at the *DHCP Server* field. It will show the IP of your first DHCP server.

<img width="1109" height="627" alt="image" src="https://github.com/user-attachments/assets/6d55621a-c6c6-4457-8ece-93d065587b4b" />

---

Now power off your first DHCP server and then on the client machine request new IP address again.

Check your IP configuration. Now the *DHCP Server* field shows IP of our second DHCP server.

<img width="1110" height="621" alt="image" src="https://github.com/user-attachments/assets/94b45bc5-02b7-470b-9e87-bca9cff822a4" />

## Validation trough PowerShell

Useful commands:

- Get-DhcpServerv4Failover - Display DHCP failover relationships
- Get-DhcpServerv4Scope - Display configured IPv4 scopes
- Get-DhcpServerv4Lease -ScopeId 192.168.234.0 - Display active DHCP leases
- Get-DhcpServerInDC - Display authorized DHCP servers in Active Directory

<img width="1114" height="627" alt="image" src="https://github.com/user-attachments/assets/1ebbd57d-2fb5-4b00-9fd5-dace87e35d09" />

<img width="1114" height="627" alt="image" src="https://github.com/user-attachments/assets/d35836da-b711-4580-a867-0be122893213" />

<img width="1108" height="625" alt="image" src="https://github.com/user-attachments/assets/84482079-30af-428c-9c40-7714e88b6998" />

<img width="1114" height="625" alt="image" src="https://github.com/user-attachments/assets/b27da855-1020-4fa2-9bc1-1f90a8611778" />





















