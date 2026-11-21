# windows-server-lab
Hands-on Windows Server administration labs: VMware setup, Active Directory, DNS, DHCP and Group Policy.
# Lab: Installing Windows Server 2022 on VMware Workstation

**Date:** 2026-11-21
**Environment:** VMware Workstation Pro 17 (VM name: `DC`)
**Reference:** Windows Server administration lab series

---

## 🎯 Objective

Create a virtual machine and install Windows Server 2022 from an ISO image, as the base for a future Active Directory lab.

---

## 1. Creating a New Virtual Machine

From the VMware Workstation home page, click **Create a New Virtual Machine**.

---

## 2. Selecting the Installation Source

In the **New Virtual Machine Wizard**:

- Choose **Installer disc image file (iso)**.
- Click **Browse...** and select the Windows Server 2022 ISO.

**Observation:** VMware detects the OS from the ISO (for example "Windows 11 x64 detected"), so the detection message is a quick way to confirm you picked the right file.

---

## 3. Selecting the Guest Operating System

```text
Guest operating system: Microsoft Windows
Version:                Windows Server 2022
```

This lets VMware apply suitable default hardware settings and drivers.

---

## 4. Naming the VM and Setting Hardware

| Setting | Value |
|---|---|
| VM name | `DC` |
| vCPUs | _(fill in)_ |
| RAM | _(fill in)_ |
| Disk size | _(fill in)_ |
| Network | _(NAT / Host-only / Bridged)_ |

---

## 5. Starting the Installation

Power on the VM and let the installer boot.

VMware shows: *install Windows Server 2022 as you would on a physical computer, then click "I Finished Installing"*.

**Tip:** press `Ctrl + Alt` to release the mouse cursor from the VM.

---

## 6. Choosing the Installation Type

| Option | When to use |
|---|---|
| **Upgrade** | Only when a supported OS is already installed and you want to keep files and apps |
| **Custom (advanced)** | Clean install on a new, blank disk ✅ |

For a new VM, choose **Custom**.

---

## 7. Installation Progress

The installer goes through these stages and restarts the VM several times:

```text
1. Copying Microsoft Server Operating System files
2. Getting files ready for installation
3. Installing features
4. Installing updates
5. Finishing up
```

---

## 8. After Installation

- Set the **Administrator** password.
- Log in with **Send Ctrl+Alt+Del** from the VMware menu.
- Click **I Finished Installing** in VMware.
- Install **VMware Tools**.
- Take a **snapshot** named `clean-install`.

---

## 9. Common Mistakes and Fixes

| Mistake | Result | Fix |
|---|---|---|
| Selecting a Windows 11 ISO | Wrong OS gets installed | Choose the Windows Server 2022 ISO |
| Choosing **Upgrade** on a blank disk | Option not usable | Choose **Custom** |
| Mouse stuck inside the VM | Cannot reach the host | Press `Ctrl + Alt` |
| Guest OS version mismatch | Wrong default hardware | Select **Windows Server 2022** |

---

## 📌 Steps Summary

| Step | Action |
|---|---|
| 1 | Create a New Virtual Machine |
| 2 | Select the Windows Server 2022 ISO |
| 3 | Guest OS: Windows, Version: Windows Server 2022 |
| 4 | Name the VM (`DC`) and size CPU / RAM / disk |
| 5 | Power on and start Setup |
| 6 | Choose **Custom** installation |
| 7 | Wait for installation and restarts |
| 8 | Set the password, install VMware Tools, take a snapshot |

---

## 💡 Key Takeaways

1. Always verify the ISO matches the guest OS you selected.
2. **Custom** is the correct choice for a clean install; **Upgrade** needs an existing OS.
3. `Ctrl + Alt` releases the mouse from the VM.
4. Take a **snapshot** after the base install so you can roll back mistakes.
5. Use clear VM names (`DC`, `SRV1`, `CLIENT1`) to keep a lab organized.
6. Next step: static IP, then the Active Directory Domain Services role.

---

<img width="1597" height="991" alt="Screenshot 2026-11-21 221921" src="https://github.com/user-attachments/assets/728f7106-356f-4a99-b82d-7fd523c6a5f1" />
<img width="1543" height="996" alt="Screenshot 2026-11-21 221657" src="https://github.com/user-attachments/assets/f1acf3ea-a717-4a03-9793-ae6a45730c4c" />
<img width="1609" height="993" alt="Screenshot 2026-11-21 221348" src="https://github.com/user-attachments/assets/c3cb5021-c491-4eb3-a4e0-7214956022aa" />
<img width="1534" height="919" alt="Screenshot 2026-11-21 212508" src="https://github.com/user-attachments/assets/d5c997f1-93bf-4e78-b967-cb82a12d7b69" />
<img width="1702" height="985" alt="Screenshot 2026-11-21 212331" src="https://github.com/user-attachments/assets/2eb3c62e-ea2d-4da0-b9ec-3f4c4c70b64b" />
<img width="1729" height="987" alt="Screenshot 2026-11-21 212111" src="https://github.com/user-attachments/assets/c97e5738-4aa1-4f83-8330-2410a885c590" />


