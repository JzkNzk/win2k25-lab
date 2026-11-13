# Configuring Distributed File Server on Windows Server 2025

## Goals

The goal of this lab is to learn how to configure a Distributed File System (DFS) on Windows Server 2025 using DFS Namespaces and DFS Replication.

By completing this lab, you will learn how to:
- Install DFS Namespaces and DFS Replication roles on two Windows Servers.
- Create and configure a DFS Namespace using DFS Management.
- Configure a shared folder within the DFS Namespace.
- Add shared folder targets hosted on both servers.
- Configure a DFS Replication group for the shared folders.
- Select replication members and configure the replication topology.
- Understand the purpose of the primary replication member.
- Configure replication schedules and bandwidth limits.
- Verify the DFS Replication configuration in DFS Management.
- Test file replication between two servers using a Windows 11 client.

At the end of this lab, you will understand how DFS Namespaces provide a unified path to shared resources and how DFS Replication keeps files synchronized between multiple servers.

## Installing DFS on Windows Server

On your Windows Server, install DFS Namespaces and DFS Replication roles. Do this on both of your servers.

<img width="787" height="561" alt="image" src="https://github.com/user-attachments/assets/6f4169d7-72f4-4021-9a30-2a1b161006f0" />

## Configuring DFS Namespaces

Once the DFS roles are installed, from **Server Manager** open **DFS Management** window.

<img width="1058" height="706" alt="image" src="https://github.com/user-attachments/assets/f93253fb-9715-4bce-a6ac-3b15ed36ca82" /><br>

On the left-side menu navigate into **Namespaces** and select *New Namespace...*.

<img width="1058" height="706" alt="image" src="https://github.com/user-attachments/assets/f16eb1b2-66cf-44b0-99e1-381fce153970" /><br>

Select server that will be used to host the namespace.

<img width="712" height="570" alt="image" src="https://github.com/user-attachments/assets/2ece282b-447e-4778-8bcc-2f18b87b2d03" /><br>

Enter name for the namespace. This name will be used in the path to the shared folder.

<img width="713" height="571" alt="image" src="https://github.com/user-attachments/assets/ed4dae28-36d8-49fa-9329-3c664b529865" /><br>

Select *Edit Settings...* button and here specify the shared folder. You can also select permission for this folder. In this example we will give all domain user full access to the folder.

<img width="386" height="487" alt="image" src="https://github.com/user-attachments/assets/4b1981c2-5932-4ba3-a717-06a1140881e6" /><br>

<img width="360" height="448" alt="image" src="https://github.com/user-attachments/assets/226227e1-44d7-4fe6-81e6-76e3a126957f" /><br>

You can keep the **Namespace type** options as is.

<img width="714" height="570" alt="image" src="https://github.com/user-attachments/assets/b7f85b63-3cc1-4cac-944b-0d7037666965" /><br>

Once you review the namespace settings you can continue to create the namespace and the newly created namespace will be visible in the **DFS Management** window.

<img width="713" height="572" alt="image" src="https://github.com/user-attachments/assets/9efdc615-71d1-422d-a131-82a29cf1480c" /><br>

<img width="1057" height="704" alt="image" src="https://github.com/user-attachments/assets/d3d39588-1a71-47f3-b8d0-e7779ef02f6d" />

## Adding a shared folder into the DFS namespace and setting up replication

In **DFS Management* window, navigate into `Namespaces > <your-namespace>` and in the right-side menu select *New Folder...*.

Add a folder target. This can be any shared folder on your disk or you can create a new share directly from **Browse for Shared Folders** window.

The target folder's name must be the same on both of your DFS Servers.

Make sure to add folders from both of your servers.

<img width="388" height="486" alt="image" src="https://github.com/user-attachments/assets/602eeaa3-ebe0-4ac3-bad1-ab67f256b741" /><br>

<img width="393" height="415" alt="image" src="https://github.com/user-attachments/assets/10bf744e-019f-4426-80ce-3c704fcc5796" /><br>

This process will prompt you to set-up DFS Replication. Select Yes.

<img width="393" height="171" alt="image" src="https://github.com/user-attachments/assets/074d7896-2046-4ea7-9c66-85eefabfc3a6" /><br>

Go trough the **Replicate Folder Wizard**. You can keep the **Replication Group and Replicated Folder Name** as is.

<img width="716" height="568" alt="image" src="https://github.com/user-attachments/assets/da80b8f3-9ecb-4490-a77b-25dae5eba8e9" /><br>

Same for **Replication Eligibility**. Make sure the shared folder names are the same on both servers.

<img width="714" height="574" alt="image" src="https://github.com/user-attachments/assets/4bf9e9b9-aae8-4a31-84c3-46505af709a5" /><br>

Next select the primary member.

<img width="711" height="567" alt="image" src="https://github.com/user-attachments/assets/0b9d7757-3f01-4a00-b151-037e71d36b61" /><br>

Now select the topology. For two servers only mesh topology is available.

<img width="716" height="577" alt="image" src="https://github.com/user-attachments/assets/9559cfd1-e519-4dfe-83bf-63b1e43789f9" /><br>

In **Replication Group Schedule and Bandwidth** you can configure how much bandwidth will replication use. You can also configure different bandwidth values for certain time ranges.

<img width="712" height="570" alt="image" src="https://github.com/user-attachments/assets/e71bf7f0-8750-4ef3-abcf-bd35ceed75af" /><br>

Review your settings and select create. Make sure the creation is successful.

<img width="711" height="573" alt="image" src="https://github.com/user-attachments/assets/cd0d4405-39f5-4224-b310-945fcdfcd94a" /><br>

---

In the **DFS Management** window, navigate into **Replication** and make sure the configured replication is visible.

<img width="1057" height="704" alt="image" src="https://github.com/user-attachments/assets/5427b527-d500-431e-972a-d6ec8e55c646" /><br>

## Testing the namespace

Log-in into your Windows 11 client and put your DFS path into the **File Explorer**. Open the same folder using the server path for both servers in different **File Explorers**.

Create a new file in any of the open folders. The file is created and after a moment it is replicated to the second server.

<img width="1718" height="918" alt="image" src="https://github.com/user-attachments/assets/c5358dd8-cfef-4563-ad34-d3279975239d" />










