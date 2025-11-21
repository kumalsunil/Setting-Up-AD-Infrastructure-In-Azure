<p align="center">
<img width="624" height="426" alt="image" src="https://github.com/user-attachments/assets/3ca1dcc8-79de-4a2b-96a6-4769c2920658" />
</p>

# ☁️ Azure Active Directory Domain Controller Setup Guide

This tutorial details the process of deploying a foundational Active Directory environment by creating a **Domain Controller (DC-1)** and a **Client Machine (Client-1)** within Microsoft Azure, focusing on critical network and DNS configuration.

---

## 💻 Environments and Technologies Used

* **Microsoft Azure** (Virtual Machines, Networking, Resource Groups)
* **Windows Server 2022** (for Domain Controller)
* **Windows 10** (for Client Machine)
* **Active Directory Domain Services (AD DS)**

---

# 🚀 Initial Setup and Network Configuration

These steps cover the provisioning of the virtual machines and setting up the static network configuration required for domain services.

### 1. Provision VMs and Configure Network

* **1. Made 2 VMs:** Created **DC-1** (Windows Server 2022) and **Client-1** (Windows 10) in the same **Resource Group** (`AD-Lab`) and **Virtual Network** (`AD-Vnet`).
    * <img width="789" height="675" alt="Screenshot 2025-11-21 132442" src="https://github.com/user-attachments/assets/2a08279b-6af4-4e7a-9efa-1b3a571c25c6" />
    * <img width="823" height="625" alt="Screenshot 2025-11-21 132738" src="https://github.com/user-attachments/assets/49a32ccd-dcc4-4724-b863-de464aca9ba9" />
* **2. Static IP for DC-1:** Changed DC-1's Network Interface Card (NIC) Private IP address Allocation from Dynamic to **Static** (e.g., **10.0.1.4**) in the Azure Portal.
    * <img width="407" height="621" alt="Screenshot 2025-11-21 132933" src="https://github.com/user-attachments/assets/9341d9fe-603d-4659-a18b-7a619791460b" />
* **3. Firewall Disabled:** Logged into the **DC-1** VM and temporarily disabled the Windows Firewall for all profiles (Domain, Private, Public) for testing connectivity.
    * <img width="483" height="561" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/99e9a1e7-b691-4900-aeaa-1c03c6bb9459" />
* **4. DNS Set on Client-1:** Changed the **Client-1** DNS server setting in the Azure Portal to point to **DC-1's Private IP address** (e.g., **10.0.1.4**).
    * <img width="643" height="380" alt="Screenshot 2025-11-21 133440" src="https://github.com/user-attachments/assets/74bbd9bc-c47d-488e-b3ff-f689c5c7770f" />
* **5. Verified Connectivity:** Logged into **Client-1** and ran `ping 10.0.1.4` to confirm successful network communication with DC-1.
    * <img width="618" height="514" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/14fdecbe-da25-4904-9f17-3637d26b0a29" />
---

---

