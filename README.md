
<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" width="200"/>
</p>

# Configuring On-Premises Active Directory within Azure VMs

## Project Overview

Hands-on Active Directory lab deployed within Microsoft Azure virtual machines. This project demonstrates domain controller deployment, DNS configuration, client domain integration, PowerShell user automation, Group Policy management, and basic Active Directory troubleshooting.

## Objective

Build and manage a functional Active Directory environment using Azure virtual machines while gaining hands-on experience with common Windows administration and IT support tasks.

## What This Lab Covers

* Azure virtual machine and virtual network configuration
* Active Directory Domain Services (AD DS)
* Domain controller deployment
* DNS and static IP configuration
* Windows client domain joining
* Active Directory user and group management
* PowerShell user automation
* Group Policy configuration
* Account lockout and account management
* Event Viewer and security log analysis
* Remote Desktop Protocol (RDP)

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Technologies & Tools](#technologies--tools)
3. [Deployment & Configuration](#deployment--configuration)

   * [Step 1: Prepare Azure Infrastructure](#step-1-prepare-azure-infrastructure)
   * [Step 2: Deploy Active Directory](#step-2-deploy-active-directory)
   * [Step 3: Automate User Creation](#step-3-automate-user-creation)
   * [Step 4: Group Policy & Account Management](#step-4-group-policy--account-management)
4. [Code & Scripts](#code--scripts)
5. [Screenshots](#screenshots)

---

## Technologies & Tools

* **Microsoft Azure** — Virtual machines and networking
* **Active Directory Domain Services (AD DS)** — Domain and identity management
* **Group Policy Management** — Account and security policy configuration
* **PowerShell** — User account automation
* **Remote Desktop Protocol (RDP)** — Remote administration
* **Event Viewer** — Security event and account troubleshooting

### Operating Systems

* **Windows Server 2022**
* **Windows 10 (21H2)**

---

# Deployment & Configuration

## Step 1: Prepare Azure Infrastructure

The lab environment was prepared within Microsoft Azure by creating the required virtual networking and virtual machines.

### Configuration

* Created an Azure **Virtual Network**
* Deployed two virtual machines:

  * **DC-1** — Domain Controller
  * **Client-1** — Windows 10 Client
* Assigned a **static IP address** to DC-1
* Configured Client-1 to use DC-1 for **DNS**
* Verified network connectivity using:

  * `ping`
  * `ipconfig`

---

## Step 2: Deploy Active Directory

Active Directory Domain Services was installed and configured on DC-1.

### Configuration

* Installed **Active Directory Domain Services (AD DS)**
* Promoted DC-1 to a **Domain Controller**
* Created a new Active Directory forest:

  * `mydomain.com`
* Created an administrative user:

  * **Jane Doe**
* Joined Client-1 to the Active Directory domain

---

## Step 3: Automate User Creation

PowerShell was used to automate the creation of multiple Active Directory user accounts within the lab environment.

### Configuration & Testing

* Added domain users to the **Remote Desktop Users** group
* Ran a PowerShell script to bulk-create user accounts
* Verified the generated accounts in Active Directory
* Tested domain login using a sample account:

  * `nose.wed`

This provided hands-on practice with user creation and account management at scale.

---

## Step 4: Group Policy & Account Management

Group Policy and Active Directory management tools were used to configure account security settings and troubleshoot user account behavior.

### Configuration & Testing

* Configured an **Account Lockout Policy** using Group Policy Management (`gpmc.msc`)
* Tested user account lockouts
* Practiced resolving locked accounts
* Enabled and disabled Active Directory user accounts
* Reviewed security events using **Event Viewer**
* Analyzed account-related security logs

---

# Code & Scripts

During this lab, I used a **PowerShell script provided by the CourseCareers course** to automate the creation of multiple Active Directory users in the test environment.

The script was used to:

* Bulk-create Active Directory user accounts
* Test user login and authentication
* Practice Group Policy configurations
* Practice user and Organizational Unit (OU) management at scale

### Provided PowerShell Script

> **Note:** This script was provided as part of the CourseCareers course and is included for documentation of the lab environment and automation process.

```powershell
$PASSWORD_FOR_USERS = "<LAB_PASSWORD>"
$NUMBER_OF_ACCOUNTS_TO_CREATE = 10000
# ------------------------------------------------------ #

Function generate-random-name() {
    $consonants = @('b','c','d','f','g','h','j','k','l','m','n','p','q','r','s','t','v','w','x','z')
    $vowels = @('a','e','i','o','u','y')
    $nameLength = Get-Random -Minimum 3 -Maximum 7
    $count = 0
    $name = ""

    while ($count -lt $nameLength) {
        if ($($count % 2) -eq 0) {
            $name += $consonants[$(Get-Random -Minimum 0 -Maximum $($consonants.Count - 1))]
        }
        else {
            $name += $vowels[$(Get-Random -Minimum 0 -Maximum $($vowels.Count - 1))]
        }
        $count++
    }

    return $name
}

$count = 1
while ($count -lt $NUMBER_OF_ACCOUNTS_TO_CREATE) {
    $firstName = generate-random-name
    $lastName = generate-random-name
    $username = $firstName + '.' + $lastName
    $password = ConvertTo-SecureString $PASSWORD_FOR_USERS -AsPlainText -Force

    Write-Host "Creating user: $($username)" -BackgroundColor Black -ForegroundColor Cyan

    New-AdUser -AccountPassword $password `
               -GivenName $firstName `
               -Surname $lastName `
               -DisplayName $username `
               -Name $username `
               -EmployeeID $username `
               -PasswordNeverExpires $true `
               -Path "ou=_EMPLOYEES,$(([ADSI]`"").distinguishedName)" `
               -Enabled $true

    $count++
}
```

---

# Screenshots

## Step 1: Prepare Azure Infrastructure

<img width="1600" height="900" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/3e188112-bc04-4b11-b2cc-7d4e3e3e102b" />

<img width="1600" height="900" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/448988df-58d8-4f89-816b-4efebca00432" />

<img width="1600" height="900" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/fb3548d5-e406-41b7-9121-8739226a105f" />

<img width="1600" height="900" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/2ad1e1f8-cb84-4be0-8d6a-c6edb1c3b5e6" />

<img width="1600" height="900" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/f274fa19-44e6-46f4-892e-cf62db78b2f0" />

<img width="1600" height="900" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/65a4ee63-101d-402a-a10f-ba42249476ce" />

<img width="1600" height="900" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/0cf7a364-eed0-4970-b1cd-500481af57a3" />

<img width="1600" height="900" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/cd6f4f7e-9b1b-47b6-9129-6e1efb73b1c4" />

---

## Step 2: Deploy Active Directory

<img width="1600" height="900" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/08a80dab-cbd8-4ea5-9614-b295b4cf5060" />

<img width="1600" height="900" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/4eb1a98d-0839-42c7-ba1f-25c82374f044" />

<img width="1600" height="900" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/53231c82-a39d-4abd-979d-03d6adf5783d" />

<img width="1600" height="900" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/579a6e86-d202-41e1-b069-ef4a04b6c608" />

<img width="1600" height="900" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/306a9b14-2c57-4945-93ac-f457fbe9cbce" />

<img width="1600" height="900" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/7578429a-f692-4ac3-93d0-d516e8093689" />

<img width="1600" height="900" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/940d10b9-aa91-4192-8142-9a2da11d337a" />

---

## Step 3: Automate User Creation

<img width="1600" height="900" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/fc35743f-b277-41a0-9891-8a2c1e5dc665" />

<img width="1600" height="900" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/85c54199-5a74-4c09-8559-0623b7365ae8" />

<img width="1600" height="900" alt="Screenshot (35)" src="https://github.com/user-attachments/assets/6198cb05-ce8f-41c2-b46d-9c85d552f1d6" />

<img width="1600" height="900" alt="Screenshot (42)" src="https://github.com/user-attachments/assets/bc522f0c-1ccb-4e8d-92a6-6c8a41b73b40" />

---

## Step 4: Group Policy & Account Management

<img width="1600" height="900" alt="Screenshot (36)" src="https://github.com/user-attachments/assets/838d6d82-5600-41b6-b818-db36ece6d75b" />

<img width="1600" height="900" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/7afc4b66-8403-439c-9784-27f8395d9207" />

<img width="1600" height="900" alt="Screenshot (38)" src="https://github.com/user-attachments/assets/f9b53e30-d9b5-4bf8-9bd1-e5906caacc6c" />

<img width="1600" height="900" alt="Screenshot (39)" src="https://github.com/user-attachments/assets/788e1686-1d4c-41bc-b3c3-bc7ab743a00f" />

<img width="1600" height="900" alt="Screenshot (40)" src="https://github.com/user-attachments/assets/a61bbf8e-7f9c-41da-af07-bb029eb1c9c3" />

<img width="1600" height="900" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/9a2fe2e2-806c-46b6-8556-6c8ab960d6b1" />





















