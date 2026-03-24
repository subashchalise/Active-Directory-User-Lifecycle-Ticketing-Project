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

---

### 🟢 Ticket 1: New Hire Onboarding
> **Problem:** A new hire, **Sarah Jenkins**, requires specialized access to the IT department. A new account and group membership must be provisioned following the company's OU hierarchy.

#### **Technical Actions:**
* **Provisioning:** Created the user object `sjenkins` within the **FCTS > Users > IT** Organizational Unit.
* **Access Control:** Established the `IT-Group` Security Group in the **Groups** OU and assigned Sarah as a primary member.
* **Verification:** Authenticated onto the **Windows 11 Client** as `sjenkins`. Executed `whoami /groups` to verify that the **ACILABS\IT-Group** SID was successfully injected into the user's access token.

#### **📸 Technical Evidence:**

| **Step 1: User Creation** | **Step 2: ADUC Verification** | **Step 3: Group Membership** | **Step 4: Client Proof** |
| :---: | :---: | :---: | :---: |
| ![User Creation](images/ticket2a.png) | ![OU Verification](images/ticket2b.png) | ![Group Member](images/ticket2c.png) | ![whoami Command](images/ticket2d.png) |

---

---

