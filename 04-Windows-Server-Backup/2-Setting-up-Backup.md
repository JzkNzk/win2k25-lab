# Setting up backup in Windows Server

## Goals

The goal of this lab is to learn how to configure and perform a basic backup in a Windows Server environment.

By completing this lab, you will learn how to:

- Install the Windows Server Backup feature using the Add Roles and Features Wizard.
- Open and navigate the Windows Server Backup tool.
- Configure a one-time backup using the Backup Once option.
- Select specific items to include in the backup.
- Choose a separate backup disk as the backup destination.
- Start the backup process and monitor its progress.
- Verify that the backup has completed successfully.

At the end of this lab, you will be able to perform a basic manual backup of selected data using Windows Server Backup.

## Installing Windows Server Backup

Open **Add Roles and Features Wizzard** and install the **Windows Server Backup** feature on your server.

<img width="784" height="557" alt="image" src="https://github.com/user-attachments/assets/8c4b3610-46dd-4c0d-86e9-ba583ca0f732" /><br>

<img width="784" height="556" alt="image" src="https://github.com/user-attachments/assets/ad312ced-0ae9-4fe5-9598-423e62ecc5d5" /><br>

## Setting up Backup

Once the feature is installed navigate into Server Manager and open **Windows Server Backup** tool.

In the left menu, select *Local Backup*. It will take a few seconds to load up.

In the right menu, select *Backup Once...* and go trough the wizard.

Select custom backup configuration and continue. Add items you want to backup and select OK. As backup destination, select the new backup disk.

Confirm your backup settings and select *Backup*. It will take a while to backup all the items.

<img width="668" height="553" alt="image" src="https://github.com/user-attachments/assets/2670359b-8435-446b-8117-3791770f962f" /><br>

<img width="669" height="555" alt="image" src="https://github.com/user-attachments/assets/fd2811be-7adb-4c93-a8e7-74f9f9083d10" /><br>

<img width="673" height="556" alt="image" src="https://github.com/user-attachments/assets/9c5a5635-5895-41d2-ba6e-f2ae5d91edfd" /><br>

<img width="674" height="553" alt="image" src="https://github.com/user-attachments/assets/d629a76f-ecb3-4b6e-afc6-4c7b81d692bb" /><br>

<img width="671" height="553" alt="image" src="https://github.com/user-attachments/assets/ec1555fd-dc5e-4219-89c0-7571b7fdc9b3" /><br>

<img width="670" height="553" alt="image" src="https://github.com/user-attachments/assets/dfe16a40-11aa-4b30-aa61-6aaff9b5c0eb" /><br>

<img width="673" height="553" alt="image" src="https://github.com/user-attachments/assets/bd0d5d47-21df-47f2-9844-e94a097f25ed" /><br>

Once the backup is done there will be a message indicating a the new backup.

<img width="1719" height="918" alt="image" src="https://github.com/user-attachments/assets/a0dce4c9-5f7b-48d8-8bd8-d0b404cf9f65" />


