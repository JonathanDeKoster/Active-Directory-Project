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
5. [Learning Outcomes](#learning-outcomes)  
6. [Code & Scripts](#code--scripts)  

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

<img width="1600" src="https://github.com/user-attachments/assets/0a61881b-dd78-47ee-984c-0894681b19fd" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/1b48f07b-c7f2-4eda-8733-28e03a03f716" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/2206ac3d-3da2-4036-95c6-5d0302204d91" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/c804a2f0-d4eb-4771-9557-6356f768134e" />  

</details>


---

### ***Step 4: Group Policy & Account Management***
- Configure Account Lockout Policy via gpmc.msc.

- Test user lockouts and resolutions.

- Enable/disable accounts in AD.

- Audit security logs in Event Viewer.

<details>
<summary>📸 Click to view Step 4 screenshots</summary>

<img width="1600" src="https://github.com/user-attachments/assets/34af0a1c-964d-4cb8-be65-8f18c8579f6c" /> 

---

<img width="1600" src="https://github.com/user-attachments/assets/050df9ef-987e-4a4a-aea2-6abe38043649" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/4f8ac407-d5af-4910-80ca-00641995f28b" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/192b9e7e-186c-441a-9ab0-10afb3e024c7" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/368a787c-9b71-4c5d-a7d6-ef5a50b5bbb2" />  

---

<img width="1600" src="https://github.com/user-attachments/assets/4f1294b2-7252-4086-b64f-b825d06796d8" />  

</details>  


---



### ***Learning Outcomes***
- Built an Active Directory lab in Azure from scratch.

- Configured networking, DNS, and IP settings for domain environments.

- Automated user creation and management using PowerShell.

- Applied Group Policies for security and account management.

- Gained hands-on experience troubleshooting AD logs and security events.


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









