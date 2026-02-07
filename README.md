# Configuring On-Premises Active Directory within Azure VMs 

<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo" width="200"/>
</p>

**Project Overview**

Hands-on Active Directory lab deployed entirely within Microsoft Azure virtual machines. Demonstrates practical skills in domain controller setup, client integration, PowerShell automation, and group policy management.

**Objective**

Gain experience deploying and managing a functional Active Directory environment in the cloud, simulating real-world IT support and system administration tasks.

**What This Lab Covers**

- Preparing Azure infrastructure including VMs, networking, and IP configuration

- Deploying Active Directory Domain Services and joining client machines to the domain

- Automating user and group creation using PowerShell scripts

- Configuring and managing users, groups, and policies via Group Policy Objects (GPOs)


**Learning Outcomes**
- Built an Active Directory lab in Azure from scratch.

- Configured networking, DNS, and IP settings for domain environments.

- Automated user creation and management using PowerShell.

- Applied Group Policies for security and account management.

- Gained hands-on experience troubleshooting AD logs and security events.

---

## **Table of Contents**  
1. [Overview](#overview)  
2. [Video Demonstrations](#video-demonstrations)  
3. [Technologies & Tools](#technologies--tools)    
4. [Deployment & Configuration](#deployment--configuration)  
   - [Step 1: Prepare Azure Infrastructure](#step-1-prepare-azure-infrastructure)  
   - [Step 2: Deploy Active Directory](#step-2-deploy-active-directory)  
   - [Step 3: Automate User Creation](#step-3-automate-user-creation)  
   - [Step 4: Group Policy & Account Management](#step-4-group-policy--account-management)   
5. [Code & Scripts](#code--scripts)  

---

## **Overview**

This project demonstrates how to deploy a fully functional Active Directory lab in Azure, including domain controllers, client machines, PowerShell automation, and Group Policy management.

Key Steps / Highlights:
1. Prepare Azure infrastructure: VMs, networking, IP settings.
2. Deploy Active Directory Domain Services and join client to the domain.
3. Automate user creation with PowerShell scripts.
4. Configure and manage users, groups, and policies via Group Policy.


---

## **Video Demonstrations**  

### Step 1: Preparing Active Directory  
[![Step 1: Preparing Active Directory](https://img.youtube.com/vi/LecWaZvwVhA/hqdefault.jpg)](https://youtu.be/LecWaZvwVhA)  

### Step 2: Deploying Active Directory  
[![Step 2: Deploying Active Directory](https://img.youtube.com/vi/P3ETSjE38Co/hqdefault.jpg)](https://youtu.be/P3ETSjE38Co)  

### Step 3: Creating Users  
[![Step 3: Creating Users](https://img.youtube.com/vi/9BPQEOOHzIU/hqdefault.jpg)](https://youtu.be/9BPQEOOHzIU)  

### Step 4: Group Policy Management  
[![Step 4: Group Policy Management](https://img.youtube.com/vi/u01zGACmFpI/hqdefault.jpg)](https://youtu.be/u01zGACmFpI)  

---

## **Technologies & Tools**  
- **Microsoft Azure (VMs, Networking)**  
- **Active Directory Domain Services (AD DS)**  
- **Group Policy Management**  
- **PowerShell Scripting**  
- **Remote Desktop Protocol (RDP)**  

### Operating Systems  
- **Windows Server 2022**  
- **Windows 10 (21H2)**  

---

## **Deployment & Configuration**  

### **Step 1: Prepare Azure Infrastructure**  
- Create a **Virtual Network**.  
- Deploy 2 VMs:  
  - **DC-1 (Domain Controller)**  
  - **Client-1 (Windows 10 Client)**  
- Assign **static IP** to DC-1.  
- Configure **DNS** on Client-1 to point to DC-1.  
- Verify connectivity (`ping`, `ipconfig`).  

<details>
<summary>📸 Click to view Step 1 screenshots</summary>

<img width="1600" height="900" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/3e188112-bc04-4b11-b2cc-7d4e3e3e102b" />
  

---
<img width="1600" height="900" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/448988df-58d8-4f89-816b-4efebca00432" />

---
<img width="1600" height="900" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/fb3548d5-e406-41b7-9121-8739226a105f" />
 

---
<img width="1600" height="900" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/2ad1e1f8-cb84-4be0-8d6a-c6edb1c3b5e6" />

---
<img width="1600" height="900" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/f274fa19-44e6-46f4-892e-cf62db78b2f0" /> 

---
<img width="1600" height="900" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/65a4ee63-101d-402a-a10f-ba42249476ce" />

---
<img width="1600" height="900" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/0cf7a364-eed0-4970-b1cd-500481af57a3" />

---
<img width="1600" height="900" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/cd6f4f7e-9b1b-47b6-9129-6e1efb73b1c4" /> 

</details> 


---

### **Step 2: Deploy Active Directory**  
- Install **AD DS** on DC-1.  
- Promote DC-1 as **Domain Controller** and create a new forest: `mydomain.com`.  
- Add admin user (**Jane Doe**).  
- Join Client-1 to the domain.  

<details>
<summary>📸 Click to view Step 2 screenshots</summary>

<img width="1600" height="900" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/08a80dab-cbd8-4ea5-9614-b295b4cf5060" />

---
 
<img width="1600" height="900" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/4eb1a98d-0839-42c7-ba1f-25c82374f044" />

---
<img width="1600" height="900" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/53231c82-a39d-4abd-979d-03d6adf5783d" />

---

<img width="1600" height="900" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/579a6e86-d202-41e1-b069-ef4a04b6c608" />

---

<img width="1600" height="900" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/306a9b14-2c57-4945-93ac-f457fbe9cbce" />

---  
<img width="1600" height="900" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/7578429a-f692-4ac3-93d0-d516e809368d" />

---  
<img width="1600" height="900" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/940d10b9-aa91-4192-8142-9a2da11d337a" />

</details>  



---


### **Step 3: Automate User Creation**  
- Add domain users to **Remote Desktop Users** group.  
- Run PowerShell script to bulk-create users.  
- Test login with sample user account (**nose.wed**).

<details>
<summary>📸 Click to view Step 3 screenshots</summary>

<img width="1600" height="900" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/fc35743f-b277-41a0-9891-8a2c1e5dc665" />

---
 
<img width="1600" height="900" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/85c54199-5a74-4c09-8559-0623b7365ae8" />

---
 
<img width="1600" height="900" alt="Screenshot (35)" src="https://github.com/user-attachments/assets/6198cb05-ce8f-41c2-b46d-9c85d552f1d6" />

---
 
<img width="1600" height="900" alt="Screenshot (42)" src="https://github.com/user-attachments/assets/bc522f0c-1ccb-4e8d-92a6-6c8a41b73b40" />

</details>


---

### ***Step 4: Group Policy & Account Management***
- Configure Account Lockout Policy via gpmc.msc.

- Test user lockouts and resolutions.

- Enable/disable accounts in AD.

- Audit security logs in Event Viewer.

<details>
<summary>📸 Click to view Step 4 screenshots</summary>

<img width="1600" height="900" alt="Screenshot (36)" src="https://github.com/user-attachments/assets/838d6d82-5600-41b6-b818-db36ece6d75b" />

---

<img width="1600" height="900" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/7afc4b66-8403-439c-9784-27f8395d9207" />

---

<img width="1600" height="900" alt="Screenshot (38)" src="https://github.com/user-attachments/assets/f9b53e30-d9b5-4bf8-9bd1-e5906caacc6c" />

---

<img width="1600" height="900" alt="Screenshot (39)" src="https://github.com/user-attachments/assets/788e1686-1d4c-41bc-b3c3-bc7ab743a00f" />

---

<img width="1600" height="900" alt="Screenshot (40)" src="https://github.com/user-attachments/assets/a61bbf8e-7f9c-41da-af07-bb029eb1c9c3" />

---

<img width="1600" height="900" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/9a2fe2e2-806c-46b6-8556-6c8ab960d6b1" />

</details>  


---



### ***Code & Scripts***

During this lab, I used a PowerShell script provided by the course to automate the creation of multiple Active Directory users in a test environment. This script allowed me to:

- Bulk-create user accounts in Active Directory.
- Test login and Group Policy configurations.
- Practice user and OU management at scale.

  **Provided Script to Generate Users**

  
```powershell
$PASSWORD_FOR_USERS   = "Password1"
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
    $fisrtName = generate-random-name
    $lastName = generate-random-name
    $username = $fisrtName + '.' + $lastName
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









