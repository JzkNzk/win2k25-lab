# Installing Windows Server 2025

## Goals

The goal of this lab is to introduce the basic installation and initial setup of Windows Server 2025.

By completing this lab, you will learn how to:

- Create and configure virtual machines for Windows Server installation.
- Install Windows Server 2025 using the installation wizard.
- Select the appropriate Windows Server edition and installation type.
- Configure basic installation settings, including language, keyboard layout, and disk selection.
- Set up the built-in Administrator account.
- Complete the installation and access the Windows Server desktop.

At the end of this lab, you will have two fully installed Windows Server 2025 virtual machines ready for further configuration and administration.

## Setting up VM in VMware Workstation

Inside VMware, navigate into top left corner, select **File** and from the dropdown menu select *New Virtual Machine*.

<img width="620" height="274" alt="image" src="https://github.com/user-attachments/assets/2c205295-86ea-4747-b5d2-8d313451cadc" /><br>

This will open **New Virtual Machine Wizard**. Keep the typical configuration selected and click *Next*.

<img width="422" height="424" alt="image" src="https://github.com/user-attachments/assets/cb2819a7-e161-4596-81c1-89342b249c71" /><br>

In **Guest Operating System Installation** select install operating system later option.

<img width="427" height="423" alt="image" src="https://github.com/user-attachments/assets/8a93ae8f-4006-49cb-8a7d-19cf81324daa" /><br>

As a guest operating system, select Windows Server 2025

<img width="420" height="427" alt="image" src="https://github.com/user-attachments/assets/f97893ea-9db6-4c89-b1c9-48e1d19b19ee" /><br>

Next enter the name of your virtual machine and save location.

<img width="423" height="425" alt="image" src="https://github.com/user-attachments/assets/4e188ed2-fe42-4424-b938-b242728eb7ab" /><br>

You can keep the disk capacity as 60GB. Store the disk file as a one file.

<img width="419" height="423" alt="image" src="https://github.com/user-attachments/assets/8edc5e74-f3ac-42aa-9476-2def9336e5a9" /><br>

Finish the setup.

<img width="422" height="425" alt="image" src="https://github.com/user-attachments/assets/9a90aab4-5475-472c-8a0f-1eec55f22e79" /><br>

---

Once the VM is created it will show up on the left menu. Select the VM and click *Edit virtual machine settings*.

<img width="1916" height="1028" alt="image" src="https://github.com/user-attachments/assets/acd59974-b750-4bd4-b65a-0b927b660178" /><br>

Select the **Memory** setting and give the VM at least 4 GB of RAM.

<img width="755" height="727" alt="image" src="https://github.com/user-attachments/assets/77438bb8-6d63-4fce-8020-565d61b08471" /><br>

Next select the **Processor** setting and set the number of cores per processor to at least 2

<img width="752" height="728" alt="image" src="https://github.com/user-attachments/assets/276bff76-907f-447c-98bd-0a0c5872aa47" /><br>

Select the **CD/DVD (SATA)** setting, as a connection, use the ISO image file and and set it to your Windows Server ISO.

<img width="755" height="730" alt="image" src="https://github.com/user-attachments/assets/8e6a1faa-ac4e-4ad5-b64b-1191add64cd6" /><br>

Click OK and power on your virtual machine.

## Windows Server Installation steps

After your VM boots up it will take you to the **Windows Server Setup** window.

First, select your preferred language.

<img width="975" height="762" alt="image" src="https://github.com/user-attachments/assets/7ffc72ba-f65d-4729-bc79-c4f040d1e768" /><br>

Next, select your keyboard settings.

<img width="975" height="764" alt="image" src="https://github.com/user-attachments/assets/01b1850c-4f6d-4bbf-83dd-6ba3669751ee" /><br>

As a setup option, select *Install Windows Server* and mark the checkbox.

<img width="975" height="766" alt="image" src="https://github.com/user-attachments/assets/2762f16b-a61e-4a1f-85bf-e92fb177aabe" /><br>

In this lab, we will use Windows Server 2025 Datacenter Evaluation (Desktop Experience).

<img width="975" height="763" alt="image" src="https://github.com/user-attachments/assets/3a0a8a43-9be5-4b48-9cbd-e190b6c8105c" /><br>

Accept the license terms.

<img width="975" height="762" alt="image" src="https://github.com/user-attachments/assets/e9d3b0b1-ed92-49f2-9f3e-80029a809bb1" /><br>

Next, Select your disk as a install location for Windows Server.

<img width="975" height="768" alt="image" src="https://github.com/user-attachments/assets/956cdab2-834d-4c62-8eda-637741a1245b" /><br>

Check the recap and select *Install*.

<img width="975" height="778" alt="image" src="https://github.com/user-attachments/assets/13a1de51-e920-4c1f-87ae-37ea42979eca" /><br>

Now, the Windows Server will begin installation, this might take a while.

<img width="947" height="464" alt="image" src="https://github.com/user-attachments/assets/dadb6c21-9831-4aab-8373-bc2186659268" /><br>

---

After a while, the installation process will prompt you to setup a administration account.

<img width="975" height="527" alt="image" src="https://github.com/user-attachments/assets/97d35afc-d137-4fdd-b654-e514f12df927" /><br>

Once the installation is done you can log-in with your administrator credentials.

<img width="975" height="521" alt="image" src="https://github.com/user-attachments/assets/ea020a08-f557-4f19-890a-de9649b8d044" />






