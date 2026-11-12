
# Windows 11 Client installation guide

## Goals

The goal of this lab is to introduce the basic installation and initial configuration of Windows 11 virtual machines for use in a Windows Server environment.

By completing this lab, you will learn how to:
- Install Windows 11 on a virtual machine.
- Configure basic system settings, including language, region, and keyboard layout.
- Complete the initial Windows 11 setup (OOBE).
- Create a local user account without using a Microsoft account.
- Prepare Windows 11 clients for integration into an Active Directory domain.

At the end of this lab, you will have three fully installed Windows 11 client virtual machines ready for domain joining and further testing in a Windows Server environment.

## Setting up Windows 11 VM

Open up VMware Workstation and navigate into top left corner. Select **File** and from the dropdown menu select *New Virtual Machine...*.

<img width="684" height="276" alt="image" src="https://github.com/user-attachments/assets/eceb99be-7833-4fca-88d2-e7a01702d849" /><br>

This will open **New Virtual Machine Wizard**. Keep the typical configuration selected and click Next.

<img width="422" height="425" alt="image" src="https://github.com/user-attachments/assets/ffa891f5-f52a-4b05-8276-256d4ece0664" /><br>

In **Guest Operating System Installation** select install operating system later option.

<img width="419" height="425" alt="image" src="https://github.com/user-attachments/assets/150a1196-7386-45ce-b291-6498d0f38a28" /><br>

As a guest operating system, select Windows 11.

<img width="420" height="425" alt="image" src="https://github.com/user-attachments/assets/23ca51c1-fc35-492a-8642-73fee481ad59" /><br>

Next enter the name of your virtual machine and save location.

<img width="421" height="428" alt="image" src="https://github.com/user-attachments/assets/93049e10-c789-46a1-a868-df49bcea96ff" /><br>

Enter credentials for file encryption. You can keep the checked settings as is.

<img width="425" height="424" alt="image" src="https://github.com/user-attachments/assets/4da98c7a-fd51-47fc-aec0-cdae1e36e764" /><br>

You can keep the disk capacity as 64 GB. Store the disk file as a one file.

<img width="425" height="424" alt="image" src="https://github.com/user-attachments/assets/2a476834-8d86-4740-9895-23b30cbb1a63" /><br>

Finish the setup.

<img width="424" height="422" alt="image" src="https://github.com/user-attachments/assets/9103f62c-2f5e-4f71-b100-bf66d1007045" /><br>

---

Once the VM is created it will show up on the left menu. Select the VM and click Edit virtual machine settings.

<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/a5f905d2-21d7-4945-bee4-1723732adfa5" /><br>

Select the CD/DVD (SATA) setting, as a connection, use the ISO image file and and set it to your Windows 11 ISO.

<img width="752" height="730" alt="image" src="https://github.com/user-attachments/assets/b0dc5f07-47bc-48ff-b07b-7d3788b17af9" /><br>

Click OK and power on your virtual machine.

## Windows 11 Installation setps

Once your VM boots up it will open the Windows 11 Setup window

First select your preferred language settings.

<img width="975" height="763" alt="image" src="https://github.com/user-attachments/assets/e68ce044-a337-4feb-b965-720c4b43c132" /><br>

Next, select your keyboard setting.

<img width="975" height="762" alt="image" src="https://github.com/user-attachments/assets/aa610bee-a7d5-466d-aea0-ef10de666d6c" /><br>

As a setup option, select *Install Windows 11* and select the last checkbox.

<img width="975" height="769" alt="image" src="https://github.com/user-attachments/assets/46887cd8-59bf-4ad6-aa01-c0a6c210f3fb" /><br>

Next, select the disk which will be used as a Windows 11 install location.

<img width="975" height="761" alt="image" src="https://github.com/user-attachments/assets/5b8b7ad0-421d-4b49-bfa9-4ed606c30dfb" /><br>

Check the recap and continue with installation.

<img width="975" height="768" alt="image" src="https://github.com/user-attachments/assets/5f7ce7e7-4f0d-4d2e-b515-56b5ccf7712a" /><br>

Now the installation begins, this will take a while.

<img width="802" height="434" alt="image" src="https://github.com/user-attachments/assets/4d2a4311-f624-44be-a7d9-3dc242f4d971" /><br>

---

Once the initial installation is complete it will prompt you to setup your windows environment.

First, select your region.

<img width="975" height="705" alt="image" src="https://github.com/user-attachments/assets/ae181001-9f57-4bf0-94a6-db5a1e01d54f" /><br>

Next, confirm your keyboard layout.

<img width="975" height="689" alt="image" src="https://github.com/user-attachments/assets/6a479738-04c9-431d-b7d3-671108961c6b" /><br>

You can add additional keyboard layouts.

<img width="975" height="695" alt="image" src="https://github.com/user-attachments/assets/208e8065-a502-48b6-894e-9af39c981521" /><br>

Next setup your login credentials. For this lab, we don't need to use Microsoft accounts. On the sign in screen, select **Sign-in options**.

<img width="975" height="695" alt="image" src="https://github.com/user-attachments/assets/ffdb8867-786a-4817-b3e2-ebf5f037c3dd" /><br>

In the Sign-in options, select **Domain join instead**.

<img width="975" height="708" alt="image" src="https://github.com/user-attachments/assets/bd8877b1-c69a-4d21-80ae-764a1004e5d0" /><br>

Create your user, set up your password and security.

<img width="975" height="701" alt="image" src="https://github.com/user-attachments/assets/b03be287-001a-44b1-8ea1-72ae1c1da864" /><br>

<img width="975" height="696" alt="image" src="https://github.com/user-attachments/assets/973d20b2-35ee-4589-bcf7-0d471e25dc3f" /><br>

<img width="975" height="701" alt="image" src="https://github.com/user-attachments/assets/d680b203-9051-4553-b6ba-263a348490f3" /><br>

Next, setup Microsoft app and system preferences.

<img width="975" height="704" alt="image" src="https://github.com/user-attachments/assets/fd088eaf-1be4-4988-a529-a40c1da98399" /><br>

Once the environment is setup, the final part of the installation begins.

<img width="975" height="716" alt="image" src="https://github.com/user-attachments/assets/c86c71ef-54e0-473f-b1d3-461affa2a786" /><br>

Once the installation is done you can log-in to your desktop.

<img width="975" height="733" alt="image" src="https://github.com/user-attachments/assets/2b68021f-2f21-4f95-ab6f-7e3eb9dabc33" />





