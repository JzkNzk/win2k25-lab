# Restoring DC from backup

## Using Windows Backup to restore files

To restore deleted files, folders or other data, we can use **Windows Server Backup**. Open **Windows Server Backup** and in the right menu click *Recover...*.

This will open **Recover Wizard** and takes you trough the process of recovering backed up data.

You can select which backup you want to use, date of the backup, what recovery type you want to use, what files to recover and what options should the recovery use.

<img width="741" height="577" alt="image" src="https://github.com/user-attachments/assets/18bfa182-0845-4aaa-9a89-1974ee902338" />

<img width="741" height="565" alt="image" src="https://github.com/user-attachments/assets/ae943233-28d1-4157-a137-c920c9fb6398" />

<img width="738" height="579" alt="image" src="https://github.com/user-attachments/assets/1361ab99-b32d-4a73-be08-b3a04e9e1298" />

<img width="740" height="578" alt="image" src="https://github.com/user-attachments/assets/d177a2b3-38b7-42cc-98e1-f44cd8d152d8" />

## Recovering deleted drive

To recover the whole drive, power off your DC.

Open your DC VM settings, select your main drive, copy the path where the drive is located, remove the main drive and then paste the copied path into file explorer.

Find your main drive (vmdk) in the VM folder and delete it.

<img width="754" height="728" alt="image" src="https://github.com/user-attachments/assets/bfb579c5-f505-4aa9-985d-ecbdd587adfc" />

<img width="1902" height="604" alt="image" src="https://github.com/user-attachments/assets/440854df-62c1-4de2-9e59-b44784d48108" />

Then once again create a new hard disk for the DC VM.

<img width="752" height="727" alt="image" src="https://github.com/user-attachments/assets/86253817-ed74-4cb0-bad1-a958d0b4eb21" />

You also need to add a CD/DVD into the VM and select your Windows Server ISO.

<img width="751" height="723" alt="image" src="https://github.com/user-attachments/assets/a45a5080-b29a-4b5f-b90a-78bccc608332" />

Power on the VM and in a moment the **Windows Server Setup** screen will show up. Click next until you see **Select setup option** screen and select *Repair my PC* and select next.

<img width="1020" height="769" alt="image" src="https://github.com/user-attachments/assets/b7afd8d8-c65f-462d-9266-53d771d1275f" />

<img width="1022" height="772" alt="image" src="https://github.com/user-attachments/assets/56ee77d2-8c83-40bd-bbb7-234f0ba1f66d" />

Next select `Troubleshoot > System Image Recovery `

<img width="1027" height="768" alt="image" src="https://github.com/user-attachments/assets/00571c4d-58ee-4b53-93ce-2e00f6c671bd" />

<img width="1020" height="768" alt="image" src="https://github.com/user-attachments/assets/6e2f7089-e92f-4bbe-bfc5-f1c3f55b6735" />

Next you can select your last backup and then select time and date of the backup. Click next and Finish and the restoring process will start.

<img width="507" height="401" alt="image" src="https://github.com/user-attachments/assets/3393ca32-29c1-4005-9522-3a0c779eea87" />

<img width="1026" height="767" alt="image" src="https://github.com/user-attachments/assets/52e07e62-4649-4e3d-9f53-041c88d055e3" />

<img width="1024" height="769" alt="image" src="https://github.com/user-attachments/assets/c6a8f098-acbe-4e75-9733-ff7aca8c80c0" />

<img width="1026" height="770" alt="image" src="https://github.com/user-attachments/assets/89deb027-aefc-43ba-aa2b-95a679796980" />

<img width="1026" height="770" alt="image" src="https://github.com/user-attachments/assets/9a55f7af-5686-4982-bb25-0561b4b36384" />

Once the restoring process is done the DC will restart.

<img width="1717" height="920" alt="image" src="https://github.com/user-attachments/assets/28819ed6-a656-4546-8a02-cc3eefec3fce" />























