## Login with our domain Administrator account
<img width="1717" height="918" alt="image" src="https://github.com/user-attachments/assets/928affc4-2a4f-4d75-bfad-886f9d343a0f" />

## Install AD DS with Role-Based installation
<img width="784" height="564" alt="image" src="https://github.com/user-attachments/assets/6fa86028-2dc1-4e7f-8baa-43f32fdfc3e1" />

## Once the installation is complete we enter AD DS Configuration wizzard (promote server to domain controller)

We can keep the option to make this server a domain controller and click next.
<img width="750" height="557" alt="image" src="https://github.com/user-attachments/assets/323face5-4adf-4839-8e3c-05f7d5b310f3" />

On the next screen we can also keep the pre-selected options, type in DSRM password and click next.
<img width="754" height="555" alt="image" src="https://github.com/user-attachments/assets/3ae57418-a427-4c3e-8226-e544f88844f6" />

On Additional Options screen in **Replicate from:** we select our main DC.
<img width="756" height="558" alt="image" src="https://github.com/user-attachments/assets/77eacb52-34d3-4550-93d4-bfd9d391d6fe" />

Once we get on Prerequisites Check screen we make sure there are no errors which would prevent the installation and click install.
<img width="760" height="557" alt="image" src="https://github.com/user-attachments/assets/80fcabea-bd58-4ae7-8157-a0105330c681" />

After installation the server reboots.

## Verifying installation
After installation we verify if everything was configured succesfully.
First let s check **Active Directory Users and Computers**. We should see the same folder structure we created on our main DC.
<img width="679" height="570" alt="image" src="https://github.com/user-attachments/assets/03b220b2-8267-4d88-8fb6-ae2db6ba45a3" />

Next we verify DNS. In **DNS Manager**, we should see our Domain folder with 2 name servers (NS).
<img width="863" height="425" alt="image" src="https://github.com/user-attachments/assets/6445b7b0-db04-45ab-a463-5d10b5c4da7f" />

The `nslookup` command should also return 2 DNS addresses.
<img width="1110" height="621" alt="image" src="https://github.com/user-attachments/assets/c8a421d4-2019-4371-9acd-027b6929f17e" />

Next thing we can check is **AD Administrative Center**. We should see again our domain with correct folder structure.
<img width="1717" height="838" alt="image" src="https://github.com/user-attachments/assets/e4bf93ff-20e1-4800-9b3b-5208a6d4b191" />

Next in **AD Sites and Services** we should see 2 servers.
<img width="967" height="297" alt="image" src="https://github.com/user-attachments/assets/385a332e-4fde-479d-bda1-a77ccc703504" />

We can also chceck if we can see NETLOGON and SYSVOL shared folders. We can use command `net share` in powershell.
<img width="1110" height="623" alt="image" src="https://github.com/user-attachments/assets/0fa9f1fc-cbf6-4bfe-b32c-ac0e083ecadb" />

We can also check this trough File Explorer where we put *our-DC02-name* into link field
<img width="1124" height="591" alt="image" src="https://github.com/user-attachments/assets/cf2397a2-2812-4cd1-984d-306f1decf394" />

Lastly, we can chceck if everything is running with this powershell command `Get-Service -Name NTDS, DNS, DFSR, KDC, Netlogon | Select-Object DisplayName, Status, StartType`
<img width="1106" height="623" alt="image" src="https://github.com/user-attachments/assets/2da192e5-fa26-4846-aa22-5a36d13f5758" />




