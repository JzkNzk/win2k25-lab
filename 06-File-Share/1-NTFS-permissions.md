# Setting up file sharing on Windows Server 2025 using NTFS permissions

## Setting-up a new drive

Set up a new drive which fill be used for sharing folders and files.

Open up **Disk Management** and initialize the new drive. Create a new volume, assign a letter to the drive and set it online.

<img width="750" height="543" alt="image" src="https://github.com/user-attachments/assets/c822c16a-1489-45a8-a5eb-822274ee3540" />

<img width="1124" height="594" alt="image" src="https://github.com/user-attachments/assets/2d58a4f5-aa5d-4bfa-b59c-54b58ac1bcf4" />

## Folder and file sharing

On the new drive, create a following folder structure:

```
F:\CompanyData\
│
├── HR\
│   ├── Employees\
│   └── Payroll\
│
├── IT\
│   ├── Scripts\
│   └── Documentation\
│
├── Sales\
│
└── Public\
```

Share the `CompanyData` folder.

Right-click the folder and select *Properties*. Navigate into **Sharing** section and select *Advanced Sharing...*. Enable *Share this folder*, Apply and then OK.

A network path will be now visible in the sharing section.

<img width="1121" height="589" alt="image" src="https://github.com/user-attachments/assets/f05523c8-62c1-4867-82a9-b6b34413ce82" />

<img width="363" height="476" alt="image" src="https://github.com/user-attachments/assets/871d5f6b-68d7-4130-927e-d8b29ed19f7a" />

<img width="352" height="361" alt="image" src="https://github.com/user-attachments/assets/147e8128-aed2-4f73-86f5-3758cc59aa63" />

<img width="361" height="478" alt="image" src="https://github.com/user-attachments/assets/3a318843-0554-473f-b391-602e65cdad9e" />

---

You can now access the folder from other devices in the domain.

To make sure switch to a Windows 11 client machine, open **File Explorer** and in the search bar type the network path of `CompanyData` folder. 

<img width="1718" height="919" alt="image" src="https://github.com/user-attachments/assets/12294b13-e19f-49d1-915c-9b8622e4a0a7" />

## Setting up SMB permissions

Folder `CompanyData` is now accessible trough other devices in the domain, however they can only view the contents of the folders and can't modify them or create new files. To fix this we need to set up SMB permissions.

On Windows Server open **Computer Management** and in the left menu navigate to `Computer Management > System Tools > Shared Folders > Shares`. Right-click on `CompanyData` share and select properties. Select **Share Permissions** section and select **Allow** for full control in permissions for everyone.

Select Apply then OK.

This setting will make sure that users in our domain can modify the contents of all shared folders inside `CompanyData` folder and can be further managed with NTFS permissions.

<img width="986" height="704" alt="image" src="https://github.com/user-attachments/assets/fb2302bf-8b02-4c89-b399-08e904948046" />

<img width="982" height="705" alt="image" src="https://github.com/user-attachments/assets/9f1581a8-927b-48d2-827e-e28bb9043651" />

<img width="397" height="450" alt="image" src="https://github.com/user-attachments/assets/0579ce48-3153-4131-9080-a33f3a9aa0af" />


## Setting up NTFS permissions

We want user to access and modify their corresponding folders, while others should have restricted access to folders that do not belong to them.

For example, let's make `HR` folder accessible to **HR** users and **IT** users. **HR** user should have full control over `HR` folder, meaning they will be able to open all of the folders inside and create and edit new folders and files, while IT users will be able to open all of the files but can't modify them.

Permission table for `HR` folder:

| Group | Permissions            |
|-------|------------------------|
| HR    | Read, Write, Execute   |
| IT    | Read                   |

On Windows Server, open the **File-Share** disk and navigate into `CompanyData` folder.

Open HR folder properties, navigate into **Security** section and select *Edit* to change permissions. Select *Add...* and add HR and IT groups.

For HR keep the permissions as is. Select IT group and in the permissions section select **Deny** for *Write* permission.

Select Apply then OK.

<img width="364" height="480" alt="image" src="https://github.com/user-attachments/assets/15e860db-1892-41c4-89ed-f6c82c5b6e45" />
<img width="362" height="450" alt="image" src="https://github.com/user-attachments/assets/a83c84ac-2e4e-47e9-b466-cdabf4fd786c" />
<img width="359" height="448" alt="image" src="https://github.com/user-attachments/assets/f1d4525e-1481-4426-9461-930b37e51264" />

---

To make sure switch back to Windows 11 Client and log-in as a IT user. Navigate into the shared `CompanyData` folder and try to create a file inside the `HR` folder. It will show that access is denied. The same will happen when trying to dele a existing folder.

<img width="827" height="703" alt="image" src="https://github.com/user-attachments/assets/c798d969-1986-4dfe-811d-b42d3626f1ac" />

<img width="826" height="702" alt="image" src="https://github.com/user-attachments/assets/c4e68809-bd4c-4f51-aa82-cf0af1891d6f" />

---

Next log-in with HR user. Whit HR account you can freely create new files in the `HR` folder. 

<img width="1120" height="589" alt="image" src="https://github.com/user-attachments/assets/510f8610-0889-47f7-b7c5-f4446ec780ae" />

## Inheritance

Now let's try creating a file with Sales user. Will it work ? Yes it will. 

<img width="1121" height="589" alt="image" src="https://github.com/user-attachments/assets/c741636d-beb7-4764-9848-550e5ecaac23" />

---

The Sales user can still access and modify the HR folder even though no permissions have been explicitly assigned to the Sales group.

This happens because the HR folder inherits NTFS permissions from its parent folder, CompanyData. These inherited permissions allow users to access and modify the folder contents.

To restrict access, we can disable permission inheritance on the HR folder and remove inherited permissions that are no longer required. We can then explicitly assign permissions only to the groups that should have access.

This approach is easier to manage than manually denying access to every group that should not have access to the folder.


Open `HR` folder properties, navigate into **Security** section and select *Advanced*. In the **Advanced Security Settings for HR** window select *Disable inheritance*. In this scenario, select *Convert inherited permissions...*.

In **Permission entries** section find `Users` groups and remove them.

Select Apply then OK

<img width="751" height="477" alt="image" src="https://github.com/user-attachments/assets/753c8ec7-1373-4e41-a418-2359ecb600fa" />

<img width="763" height="521" alt="image" src="https://github.com/user-attachments/assets/cbca9caa-0a00-416f-8d37-d1437e6d14b3" />

<img width="751" height="478" alt="image" src="https://github.com/user-attachments/assets/5f9e5210-c738-4108-a1b9-2fdecf5634d5" />

---

Go back to Windows 11 client and log-in with Sales user credentials. Open the shared `CompanyData` folder and open `HR` folder. Now Sales user can't access the `HR` folder.

<img width="1123" height="591" alt="image" src="https://github.com/user-attachments/assets/eb52e3e4-2a6e-4a4e-9f8d-d2bc24358184" />










