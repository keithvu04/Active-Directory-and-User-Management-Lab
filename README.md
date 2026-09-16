# Active-Directory-and-User-Management-Lab

## Overview

This project demonstrates the deployment and configuration of a 
cloud-based Active Directory environment using Microsoft Azure.

The lab consists of a Windows Server 2022 domain controller (DC01) 
and a Windows 11 client (CLIENT01). The environment was configured to 
demonstrate Active Directory Domain Services, DNS, domain joining, 
user management, organizational units, and authentication.

## Technologies Used

- Microsoft Azure
- Windows Server 2022
- Active Directory Domain Services (AD DS)
- DNS
- Active Directory Users and Computers (ADUC)
- Remote Desktop Protocol (RDP)
- Azure Virtual Networks

## Network Architecture

DC01
- Role: Domain Controller / DNS Server
- OS: Windows Server 2022
- Private IP: Static

CLIENT01
- Role: Domain-joined workstation
- DNS Server: DC01
- Private IP: Dynamic

Both virtual machines were deployed on the same Azure virtual
network and subnet.

## Implementation

### 1. Azure Infrastructure

Created two Azure virtual machines:

- DC01 – Windows Server 2022
- CLIENT01 – Windows client

Configured both machines on the same Azure virtual network and
subnet to allow private communication between the systems.

### 2. Domain Controller Configuration

Configured DC01 with a static private IP address.

Installed:
- Active Directory Domain Services (AD DS)
- DNS Server

Promoted DC01 to a domain controller and created the Active
Directory forest:

adlab.local

### 3. Client Domain Join

Configured CLIENT01 to use DC01's private IP address as its DNS
server.

Verified DNS and network connectivity before joining CLIENT01
to the adlab.local domain.

Successfully joined CLIENT01 to the domain and verified domain
authentication.

### 4. Active Directory Administration

Created Organizational Units (OUs) to organize Active Directory
objects.

Example structure:

adlab.local
├── Admins
├── Employees
├── Workstations
└── Domain Controllers

Created domain user accounts and configured group memberships
using Active Directory Users and Computers (ADUC).

Moved CLIENT01 into the Workstations OU.

### 5. Remote Authentication

Configured Remote Desktop permissions for a domain user.

Successfully authenticated to CLIENT01 using an Active Directory
domain account.

Verified authentication using:

whoami
echo %logonserver%

The tests confirmed that the user was authenticated through DC01
rather than a local CLIENT01 account.

## Skills Demonstrated

- Microsoft Azure VM deployment
- Windows Server administration
- Active Directory Domain Services
- DNS configuration and troubleshooting
- Domain controller deployment
- Active Directory user management
- Organizational Unit management
- Security group and permission management
