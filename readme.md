# Active Directory Group Policy Lab

This lab builds upon the Active Directory environment created in the following repository:

* [win-server-AD-lab](https://github.com/aaomio/win-server-AD-lab)

Complete the Active Directory lab before continuing.

---

## Required Downloads

### VMware Workstation Pro

* [VMware Workstation Pro](https://knowledge.broadcom.com/external/article?legacyId=2107518)

### Windows 10 Enterprise Evaluation

* [Windows 10 Enterprise Evaluation ISO](https://www.microsoft.com/en-gb/evalcenter/download-windows-10-enterprise)

---

## Lab Environment

This lab uses:

* Windows Server 2022 Domain Controller
* Windows 10 Enterprise Client
* Active Directory Domain Services (AD DS)
* Group Policy Management

The Domain Controller should already be deployed and configured from the Active Directory lab.

Create a Windows 10 Enterprise virtual machine, install the operating system and start both virtual machines before beginning the exercises.

---

## Lab Objectives

The following Group Policy Objects (GPOs) will be configured:

* Interactive logon message
* USB storage restrictions
* Account lockout policy
* Desktop wallpaper deployment
* Command Prompt restrictions

---

## Files

* [win10-domain-join.md](./win10-domain-join.md)
* [gpo-login-message.md](./gpo-login-message.md)
* [gpo-usb-storage.md](./gpo-usb-storage.md)
* [gpo-account-lockout.md](./gpo-account-lockout.md)
* [gpo-wallpaper.md](./gpo-wallpaper.md)
* [gpo-disable-cmd.md](./gpo-disable-cmd.md)

---

## Expected Outcome

After completing this lab:

* A Windows 10 Enterprise client will be joined to the Active Directory domain.
* Users will receive a logon notice before signing in.
* USB storage devices will be blocked.
* Accounts will be locked after five failed sign-in attempts.
* A managed desktop wallpaper will be deployed.
* Command Prompt access will be restricted through Group Policy.

This demonstrates centralised Windows client management using Active Directory and Group Policy.
