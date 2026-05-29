# Windows 10 Domain Join

This document describes how to prepare a Windows 10 Enterprise client and join it to an Active Directory domain.

---

## 1. Complete Windows Installation

Power on the virtual machine and complete the Windows 10 Enterprise installation.

When the account setup screen appears:

* Select **Domain Join Instead**
* Create a local administrator account
* Configure a password
* Complete the Windows setup process

---

## 2. Configure DNS

The Windows 10 client must use the Domain Controller for DNS resolution.

Open:

```text
Win + R
```

Type:

```text
ncpa.cpl
```

Open the active network adapter and configure IPv4 settings.

Example:

```text
Preferred DNS Server: 192.168.1.199
```

Replace the address with the IP address of the Domain Controller.

---

## 3. Verify Connectivity

Open Command Prompt and verify communication with the Domain Controller.

```cmd
ping 192.168.1.199
```

Verify DNS resolution.

```cmd
nslookup
```

The Domain Controller should be displayed as the DNS server.

---

## 4. Join the Domain

Open:

```text
Win + R
```

Type:

```text
sysdm.cpl
```

Select:

```text
Computer Name
```

Click:

```text
Change
```

Select:

```text
Domain
```

Enter Active Directory domain name.

Example:

```text
matrix.local
```

When prompted, enter Domain Administrator credentials.

A welcome message should confirm successful domain membership.

Restart the computer.

---

## 5. Rename the Computer

After the restart, open:

```text
Win + R
```

Type:

```text
sysdm.cpl
```

Select:

```text
Computer Name
```

Click:

```text
Change
```

Assign a suitable hostname.

Example:

```text
Desktop-Blue
```

Restart the computer.

---

## 6. Verify Domain Membership

On the Domain Controller, locate:

```text
Server Manager\Tools\Active Directory Users and Computers
```

Expand the domain and select:

```text
Computers
```

The Windows 10 client should appear in the container.

Example:

```text
Desktop-Blue
```

The Windows 10 Enterprise client is now joined to the domain and ready for Group Policy deployment.
