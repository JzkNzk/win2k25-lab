# Sharing folders using Windows File Server role

## Setting up a shared folder trough Server Manager

Before setting anything up create a new folder on your File Share Drive.

<img width="1122" height="589" alt="image" src="https://github.com/user-attachments/assets/3236951a-d522-48ff-ac84-175d048bf76d" />

---

Open **Server Manager** and navigate into `File and Storage Services > Shares`.

In the **Shares** section, open *TASKS* dropdown and select *New Share...*.

<img width="1720" height="919" alt="image" src="https://github.com/user-attachments/assets/378b142d-3eb2-4b40-852b-3762edd3bda9" />

---

Navigate trough the **New Share Wizard**. To configure basic folder sharing select *SMB Share - Quick* profile.

As a share location, pick the newly created folder in the custom path option. You can then tweak the share name and description settings.

Furthermore, you can also specify security and access settings.

In the **Permissions** section, you can select which users will have access permissions for this folder.

In this example, we will use the following permissions:

| Group | Permissions   |
|-------|---------------|
| IT    | R, -, X       |
| HR    | Access Denied |
| Sales | R, W, X       |

The new folder is now visible in the **SHARES** section.

<img width="756" height="555" alt="image" src="https://github.com/user-attachments/assets/b5b85f21-5fca-4c4a-878b-a6fd5542d1a5" />

<img width="762" height="562" alt="image" src="https://github.com/user-attachments/assets/145d7d02-0369-4ba8-8d34-a54646bfd578" />

<img width="761" height="556" alt="image" src="https://github.com/user-attachments/assets/a3a1d23c-d9be-421b-ae78-30bd7362a4ff" />

<img width="762" height="558" alt="image" src="https://github.com/user-attachments/assets/2f0f1214-f686-4079-8aa3-bc409cec17aa" />

<img width="761" height="559" alt="image" src="https://github.com/user-attachments/assets/fb6442e0-56b2-4a8c-a377-41f45f276cdb" />

<img width="761" height="557" alt="image" src="https://github.com/user-attachments/assets/0662a623-6ec5-4552-8b3b-bbd393aa9bb6" />

<img width="1720" height="924" alt="image" src="https://github.com/user-attachments/assets/1eaa71b7-3ef8-4f00-8554-df4750d410d8" />

---

Make sure the folder is shared to every user in the domain. You can check this in the **Computer Management**.

<img width="986" height="707" alt="image" src="https://github.com/user-attachments/assets/344670dc-8a95-4e74-b8ba-821dc3d54a05" />

## Validating configuration

Switch to your Windows 11 client. Log in as a Sales user and access the new shared folder. Test if you can create a new file inside the folder.

Next check if the IT user has access. He can view the contents of the folder but cannot create new files or edit existing ones.

Lastly, HR user cannot access the folder at all.

<img width="1128" height="589" alt="image" src="https://github.com/user-attachments/assets/7f3f96d8-864d-4bd3-994f-4dcc6a8698aa" />

<img width="954" height="591" alt="image" src="https://github.com/user-attachments/assets/a42abc00-476a-420a-a74e-8ed93143dcbd" />

<img width="1125" height="591" alt="image" src="https://github.com/user-attachments/assets/776e08e4-0c70-4649-89d5-4f8e05aa8132" />

## Configuring Access-Based Enumeration

To make sure ABE works as intended, create a new folders in the new share. In this example we will create a `IT` folder and `Sales` folder inside the new share.

The goal is to make these two folders visible only for their 'owners', meaning IT group should only see their `IT` folder and the `Sales` folder will be hidden for them. The same goes for Sales but with `Sales` folder as visible and `IT` folder as hidden.

In the `IT` folder share settings, disable inheritance, remove Sales group and give IT users R, W, X access. Do the same for `Sales` folder, removing IT group and giving Sales user R, W, X access.

<img width="1126" height="592" alt="image" src="https://github.com/user-attachments/assets/e4bb93e4-9620-4f37-963c-801624910871" />

<img width="363" height="481" alt="image" src="https://github.com/user-attachments/assets/c2e4a371-3dbd-4404-990d-7bb8b2a6e9e6" />

<img width="360" height="479" alt="image" src="https://github.com/user-attachments/assets/36bd4bff-0534-4373-895f-373fc3dc9a28" />

---

Go back to Windows 11 client and log-in as Sales user or IT user. In the new share, you can see only the corresponding user folder. 

<img width="951" height="590" alt="image" src="https://github.com/user-attachments/assets/dd695284-69c7-4742-bda9-85c960bce5e8" />

<img width="1121" height="589" alt="image" src="https://github.com/user-attachments/assets/0d958508-df0e-4ebc-b18e-76f1de4cd589" />








