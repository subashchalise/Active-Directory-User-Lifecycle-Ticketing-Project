# 🛠️ Active Directory User Lifecycle & Ticketing Project

## 📋 Project Overview
This project demonstrates the core responsibilities of a Tier 1/2 IT Support Technician within an enterprise Active Directory environment. Using the **JobSkillShare (JSS)** sandbox, I designed and implemented a tiered **Organizational Unit (OU)** structure, managed user lifecycles (onboarding to termination), and resolved common security tickets including account lockouts and permission management.

---

### 💻 Environment & Tools
| Component | Specification |
| :--- | :--- |
| **Lab Environment** | JobSkillShare (JSS) IT Pro Sandbox |
| **Domain Controller** | Windows Server 2022 |
| **Client Workstation** | Windows 11 Pro (Domain Joined) |
| **Domain Name** | `ACILABS.COM` |
| **Organization Name** | Forest City Tech Solutions (FCTS) |

---

### 🎯 Core Skills Demonstrated
* **Directory Services:** OU Design, Object Nesting, and Attribute Management.
* **Account Security:** Password Resets, Account Unlocks, and Force-Password-Change policies.
* **Access Control:** Security Group management and membership verification.
* **Troubleshooting:** Resolving authentication issues and Access Token refresh latencies.

---

## 📂 Active Directory Design (OU Structure)
I avoided the default "Users" container to implement a professional, scalable hierarchy under the **FCTS** root OU:

```text
ACILABS.COM (Root)
└── FCTS (Top Level OU)
    ├── Groups (Security Groups)
    ├── Users (Employee Accounts)
    │   ├── IT
    │   ├── HR
    │   └── Marketing
    └── Computers (Workstations)
```
![Onboarding Verification](images/ticket1.png)

---

## 🎫 Help Desk Ticket Simulation



---

### 🟢 Ticket 1: Infrastructure Setup & User Onboarding
> **Problem:** A new organization structure is required to manage employees by department. A new hire, **Sarah Jenkins**, requires specialized access to the IT department.

#### **Technical Actions:**
* **Provisioning:** Created the user object `sjenkins` within the **FCTS > Users > IT** Organizational Unit.
* **Access Control:** Established the `IT-Group` Security Group in the **Groups** OU and assigned Sarah as a primary member to ensure proper resource permissions.
* **Verification:** Logged into the **Windows 11 Client** workstation as `sjenkins`. Executed the `whoami /groups` command to verify that the Kerberos Security Token was correctly issued with the new group SID.

#### **📸 Portfolio Evidence (Step-by-Step):**

| **Step 1: ADUC Provisioning** | **Step 2: Group Assignment** | **Step 3: Client Verification** |
| :---: | :---: | :---: |
| ![User Creation](images/ticket1a.png) | ![Group Member](images/ticket1b.png) | ![whoami Command](images/ticket1c.png) |

---

