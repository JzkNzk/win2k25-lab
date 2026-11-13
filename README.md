# Windows Server 2025 – Active Directory & Infrastructure Administration Lab

A hands-on Windows Server lab environment focused on learning and practicing Windows infrastructure administration, configuration, and troubleshooting.

The project was built using VMware Workstation and includes multiple Windows Server 2025 virtual machines and Windows 11 clients. It covers essential services and technologies commonly used in enterprise IT environments.

The main goal of this project is to gain practical experience with Windows Server administration by deploying, configuring, testing, and troubleshooting various infrastructure services.

##Project Overview

This lab environment covers the deployment and administration of a Windows domain infrastructure, including:

- Active Directory Domain Services (AD DS)
- Domain Controllers and Active Directory replication
- DNS and DHCP services
- DHCP Failover
- Group Policy Management (GPO)
- User accounts, Organizational Units, and Security Groups
- File Server and SMB file sharing
- NTFS permissions and Access-Based Enumeration
- Distributed File System (DFS)
- Windows Server Backup and recovery
- PowerShell and infrastructure troubleshooting

## Technologies Used

| Technology | Purpose |
|---|---|
| Windows Server 2025 | Server operating system |
| Windows 11 | Domain client machines |
| VMware Workstation | Virtualization platform |
| Active Directory | Centralized identity and domain management |
| DNS | Name resolution |
| DHCP | Automatic IP address assignment |
| Group Policy | Centralized configuration and policy management |
| SMB | Network file sharing |
| NTFS | File system permissions |
| DFS | Distributed file access and replication |
| PowerShell | Server administration and troubleshooting |

## Lab Contents

The repository contains individual labs documenting the configuration and testing of different Windows Server features.

### 1. Windows Server and Client Deployment
- Installing Windows Server 2025.
- Installing Windows 11 client machines.
- Initial server and client configuration.
- Configuring hostnames, network settings, and static IP addresses.

### 2. Active Directory Domain Services
- Installing the Active Directory Domain Services role.
- Promoting the first server to a Domain Controller.
- Creating a new Active Directory forest and domain.
- Joining additional servers and Windows 11 clients to the domain.
- Creating Organizational Units, user accounts, and Security Groups.
- Deploying an additional Domain Controller.
- Configuring and verifying Active Directory replication.

### 3. DNS Configuration and Troubleshooting

- Configuring and verifying DNS settings.
- Testing DNS name resolution.
- Troubleshooting Active Directory and DNS-related issues.
- Verifying domain controller records and replication health.

### 4. Group Policy Management
- Creating and configuring Group Policy Objects.
- Applying user and computer configuration policies.
- Managing GPO links and inheritance.
- Configuring Block Inheritance and Enforced policies.
- Using Security Filtering and Delegation.
- Verifying applied policies and troubleshooting GPO issues.

### 5. DHCP Configuration and Failover
- Installing and configuring the DHCP Server role.
- Authorizing DHCP servers in Active Directory.
- Creating and configuring IPv4 scopes.
- Configuring IP address ranges, exclusions, gateways, and DNS options.
- Configuring DHCP Failover using Hot Standby mode.
- Testing failover functionality when the primary DHCP server becomes unavailable.

### 6. File Server and Permissions
- Adding and configuring virtual storage disks.
- Creating shared folders using SMB.
- Configuring SMB share permissions.
- Managing NTFS permissions for domain users and groups.
- Understanding permission inheritance.
- Configuring Access-Based Enumeration (ABE).
- Testing access restrictions using different domain accounts.

### 7. Distributed File System (DFS)
- Installing DFS Namespaces and DFS Replication roles.
- Creating and configuring a DFS Namespace.
- Adding shared folder targets hosted on multiple servers.
- Configuring DFS Replication groups.
- Testing file replication between servers.

### 8. Backup and Recovery
- Installing Windows Server Backup.
- Creating manual backups.
- Configuring backup storage.
- Recovering files and folders.
- Practicing full system recovery of a Domain Controller using a system image backup.

### 9. Infrastructure Troubleshooting
- Using PowerShell for server administration.
- Troubleshooting DNS and Active Directory issues.
- Verifying Active Directory replication.
- Using tools such as dcdiag, repadmin, nslookup, and nltest.
- Checking Windows services and infrastructure configuration.

## Learning Objectives

Through this project, I aim to:

- Develop practical Windows Server administration skills.
- Understand how core Windows infrastructure services work together.
- Gain experience managing a Windows domain environment.
- Practice configuring redundancy and high availability for selected services.
- Improve troubleshooting and problem-solving skills.
- Become more confident using PowerShell for system administration.

## Disclaimer

This project is intended for educational purposes and was developed in a virtual lab environment. It does not represent a production infrastructure.

All configurations and experiments were performed using virtual machines in VMware Workstation.
