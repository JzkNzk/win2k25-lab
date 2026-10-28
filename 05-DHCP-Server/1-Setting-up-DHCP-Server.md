# Windows Server DHCP setup

## Installing DHCP role

Open **Add Roles and Features Wizard** and install DHCP Server Role.

<img width="783" height="558" alt="image" src="https://github.com/user-attachments/assets/1027656b-7ebc-4d7c-847f-9e226cee0cd2" />

<img width="782" height="554" alt="image" src="https://github.com/user-attachments/assets/e48f816b-210a-463b-82c8-aa5209a168f1" />

---

Once the role is installed open and complete the **DHCP Post-Install configuration wizard**.

To specify the credentials to be used to authorize DHCP server in AD DS use your Administrator account.

Select Commit and check if Post-installation was successful (mine says failed because I already did this process before). 

<img width="758" height="560" alt="image" src="https://github.com/user-attachments/assets/f1f16b84-d2a6-4b48-8579-99ba2e7ded10" />

<img width="757" height="559" alt="image" src="https://github.com/user-attachments/assets/f195b5b4-59cc-4138-9998-19114976a152" />

<img width="758" height="558" alt="image" src="https://github.com/user-attachments/assets/abf3118a-f7d2-4046-91a9-9119e77dd8f5" />

## Setting up DHCP

From **Server Manager** open **DHCP**.

Navigate into `<DC.domain-name>` and right-click IPv4. Select *New Scope...* option.

<img width="1717" height="918" alt="image" src="https://github.com/user-attachments/assets/1110613b-c80d-4065-ad45-413d4a818854" />

Complete the **New Scope Wizard**. Type in Name and Description for your Scope.

Enter the IP range and the mask. You can also enter which addresses will be excluded from the pool.

Also enter the Default gateway address and DNS servers.

Finally, activate the scope and finish the wizard.

<img width="513" height="424" alt="image" src="https://github.com/user-attachments/assets/bc1a4cbe-0f43-4e11-9608-5e73fd9285ac" />

<img width="517" height="424" alt="image" src="https://github.com/user-attachments/assets/866def21-9d2a-41e4-90c9-8beae20ef3bd" />

<img width="517" height="426" alt="image" src="https://github.com/user-attachments/assets/cbcd5c73-8b16-412c-9422-2a0d40bce708" />

<img width="515" height="426" alt="image" src="https://github.com/user-attachments/assets/3e46f6fb-f425-4f3d-ba23-f64a82aac304" />

<img width="519" height="423" alt="image" src="https://github.com/user-attachments/assets/9d43265a-b5ad-4533-81ec-8cc76741747a" />

<img width="516" height="421" alt="image" src="https://github.com/user-attachments/assets/d713ec60-1e04-49c1-b601-a71010956fca" />

<img width="513" height="421" alt="image" src="https://github.com/user-attachments/assets/48b6f555-4c6c-438e-89f0-4603e32408c8" />

<img width="515" height="424" alt="image" src="https://github.com/user-attachments/assets/172c8db7-8cc0-4f65-ab27-cbec687fa266" />

<img width="515" height="421" alt="image" src="https://github.com/user-attachments/assets/a19e0afc-1130-4493-b9f1-8af58439726e" />

<img width="515" height="421" alt="image" src="https://github.com/user-attachments/assets/9e734643-7b06-450d-9700-bd07af6aef73" />

---

After completing the wizard new scope is added.

<img width="1716" height="918" alt="image" src="https://github.com/user-attachments/assets/d005fd63-8fce-410d-8352-555348347d88" />

## Setting up DHCP connection on client

Log-in into your Windows 11 client and open **Network Connections**. Open your Ethernet connection, select *IPv4* and click properties.

Select Obtain an IP and DNS server automatically options an select OK.

<img width="806" height="574" alt="image" src="https://github.com/user-attachments/assets/73733957-44cc-41b6-a852-859b3fa7571c" />

Now open terminal and check your connectivity settings with `ipconfig /all`. The client now has IP address from address range we created. The output also shows *DHCP Enabled .... Yes*.

<img width="1108" height="622" alt="image" src="https://github.com/user-attachments/assets/0401ea67-491b-4ac7-af22-a3e9bf3aeb76" />

















