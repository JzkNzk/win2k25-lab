# Basic overview of GPO configuration 

The goal of this lab is to configure basic Group Policy Objects (GPOs) and apply them to selected users and computers in an Active Directory domain.

Useful commands:
- ``gpupdate/force`` - Forces the Group Policy settings to be refreshed and reapplies all policy settings, even if they have not changed since the last update.
- ``gpresult /r`` - Displays a summary of the Group Policy settings applied to the current user and computer, including the applied GPOs.
- ``gpresult /h c:\temp\report.html`` - Generates an HTML report containing detailed information about the Group Policy settings applied to the user and computer.
- ``rsop.msc`` - Opens the Resultant Set of Policy (RSoP) console, which displays the effective Group Policy settings applied to the user and computer.

## Disable Control Panel for normal users

This policy restricts access to Control Panel and PC settings for selected users.

For start open **Group Policy Management** window and navigate to ``Forest > Domains > <domain-name> > Group Policy Objects``.

Two default GPOs are available: Default Domain Policy and Default Domain Controllers Policy.

<img width="1715" height="916" alt="image" src="https://github.com/user-attachments/assets/affd6f0e-4837-4db3-8937-9454b0ddc14b" />

Next, right-click **Group Policy Objects** and select **New** to create a new GPO.

<img width="786" height="442" alt="image" src="https://github.com/user-attachments/assets/7e4e0cf0-4ce5-4001-a98b-a5cbbbac65e0" />

Assign a descriptive name to the policy.

<img width="387" height="178" alt="image" src="https://github.com/user-attachments/assets/6eaa21c0-91da-4d3f-9b29-f0b3e6833fd1" />

Right-click the newly created GPO and select Edit.

<img width="550" height="621" alt="image" src="https://github.com/user-attachments/assets/6fe46e63-66f0-4243-8ccb-e2e73ccb6adf" />

Navigate to:

``User Configuration > Policies > Administrative Templates > Control Panel``

Locate *Prohibit access to Control Panel and PC settings* and select **Edit**.

<img width="1720" height="919" alt="image" src="https://github.com/user-attachments/assets/f5463688-4dd5-4272-bef6-4f5e41f1c3ac" />

Select **Enable** and apply settings.

<img width="683" height="633" alt="image" src="https://github.com/user-attachments/assets/338fe713-0a2d-43cd-bd1f-b18f2f135856" />

The state of modified setting should turn into *Enabled*.

<img width="678" height="262" alt="image" src="https://github.com/user-attachments/assets/45829165-a8ef-4544-aba1-297f2c9246ab" />

## Applying policies to users

Once the GPO is created and configured it has to be linked to certain users. In this example, apply this policy on HR users.
In **Group Policy Management**, go to ``Forest > Domains > <domain-name> > <domain> > Users``, right-click on ``HR_Users`` and click on **Link an Existing GPO**.

<img width="613" height="687" alt="image" src="https://github.com/user-attachments/assets/705313e9-530f-43e2-a32a-19e60f160afc" />

Select the GPO that has to be applied and hit OK.

<img width="448" height="407" alt="image" src="https://github.com/user-attachments/assets/7ee04646-250b-4cc0-97b2-d1a68d22d45b" />

Now sign in into Windows 11 client with user from group where GPO was applied.

Navigate into search panel, type ``rsop.msc``, righ click on **User Configuration** and click **Properties**. Here, the applied GPO is shown the list.

<img width="837" height="548" alt="image" src="https://github.com/user-attachments/assets/defe4772-699f-4acf-9188-606e9b95bab4" />

We can also search for which exact policies are applied to this user.

<img width="1146" height="712" alt="image" src="https://github.com/user-attachments/assets/f7b806db-fcd7-4dc6-94ba-058995dbe235" />

Using PowrShell and executing ``gpresult /r`` will show applied user policies.

<img width="1109" height="620" alt="image" src="https://github.com/user-attachments/assets/e49c5fec-6bd0-45c7-8866-307333f8e849" />

<img width="1109" height="621" alt="image" src="https://github.com/user-attachments/assets/6922c093-f23b-4956-82a0-79ffcc3f04e5" />

Opening **Control Panel** now shows an error message.

<img width="1719" height="920" alt="image" src="https://github.com/user-attachments/assets/d621874c-2723-4794-9c5f-c8aa798f0acd" />

---
However, on the same machine, different user from different group should have access to the **Control panel**. For example let`s login into this machine with user from IT group.

<img width="1718" height="921" alt="image" src="https://github.com/user-attachments/assets/577445d4-a152-40f4-a353-cef61ef1b756" />

## Configure a Legal Notice at Logon

This time, the GPO is configured an applied to machine group. The GPO creation is almost the same as before.

Start with creating a new GPO in **Group Policy Management** in ``Forest > Domains > <domain-name> > Group Policy Objects``

<img width="385" height="178" alt="image" src="https://github.com/user-attachments/assets/e0540573-48e7-4a08-8830-658313906b66" />

Locate **Interactive logon** in ``Computer Configuration > Windows Settings > Security Settings > Local Policies > Security Options``. We should see *Message text and title for users attempting to log on*.

<img width="1718" height="920" alt="image" src="https://github.com/user-attachments/assets/82209761-ad05-41bd-9b11-8f063f1acd28" />

Define both policies

<img width="413" height="505" alt="image" src="https://github.com/user-attachments/assets/695576ba-f8f9-47dc-b0b3-e1ace693a935" />

<img width="414" height="506" alt="image" src="https://github.com/user-attachments/assets/4f8e69fa-ef62-47bc-8c82-4959ba5f7968" />

<img width="1195" height="429" alt="image" src="https://github.com/user-attachments/assets/617424b3-69b7-433d-bec4-995c95c9224a" />

In ``Forest > Domains > <domain-name> > <domain> > Workstation``, link the new GPO.

<img width="1718" height="525" alt="image" src="https://github.com/user-attachments/assets/633f7d45-678b-477b-8b3e-ac795430494d" />

Next, switch to Windows 11 machine and restart the client. Once it boots up the notice message is visible.

The message appears on client computers within the OU to which the GPO is linked, provided the policy applies successfully.

<img width="1715" height="918" alt="image" src="https://github.com/user-attachments/assets/95deefa9-f628-43b3-b7c8-5558f9d4ff6e" />



