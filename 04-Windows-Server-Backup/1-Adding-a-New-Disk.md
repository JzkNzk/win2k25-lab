# Adding a new backup disk on Windows Server

## Mapping new drive

Add a new disk to your VM. This disk will be used to store the backup of your VM.

<img width="753" height="728" alt="image" src="https://github.com/user-attachments/assets/91eb68db-9f7d-4ac6-bb36-7ddeed609c16" />

On windows server, go into *Disk Management* interface. A new unknown disk is visible.

Right-click the disk block and select *Online*.

<img width="750" height="593" alt="image" src="https://github.com/user-attachments/assets/88c5ad16-7923-4cc0-84da-b06ca68ae0c5" />

Right-click the disk again and select *Initialize disk*.

<img width="742" height="589" alt="image" src="https://github.com/user-attachments/assets/065f47b4-54f3-4344-b278-83347a630c46" />

<img width="398" height="305" alt="image" src="https://github.com/user-attachments/assets/7df4b105-0177-46df-8e5f-d9d328fa8b2d" />

Once the disk is initialized a new volume must be created. Right-click the *Unallocated* block in the **Disk Management** windows and select *New Simple Volume...*.

Go trough the initialization wizzard. Make sure to format the volume with NTFS file system.

<img width="751" height="597" alt="image" src="https://github.com/user-attachments/assets/002ee337-3269-4c26-a0c8-8146e99d81b6" />

<img width="499" height="387" alt="image" src="https://github.com/user-attachments/assets/946a9f9c-8106-41a7-9bd4-f30b195b74a7" />

<img width="495" height="386" alt="image" src="https://github.com/user-attachments/assets/bdf950f0-c87f-42e1-bc16-bed49a619fdf" />

<img width="497" height="389" alt="image" src="https://github.com/user-attachments/assets/c7f4bc51-144c-4361-b631-26a065f183c5" />

<img width="496" height="390" alt="image" src="https://github.com/user-attachments/assets/47111902-e494-4f55-9b5e-b437a596716d" />

<img width="495" height="390" alt="image" src="https://github.com/user-attachments/assets/779eafaf-8adb-4a23-9ca7-855e25b7bdcd" />

Once the new volume is created, open **File Explorer** and select *This PC*. The new disk is visible now.

<img width="1122" height="589" alt="image" src="https://github.com/user-attachments/assets/67336437-99ec-49c2-9fb4-a214965822d6" />


