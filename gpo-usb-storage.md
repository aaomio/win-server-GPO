# USB Storage Restriction (GPO)

This policy prevents users from using USB storage devices such as flash drives and external drives.

It is used to reduce data leakage risk and enforce endpoint security.

---

## 1. Open Group Policy Management

On the Domain Controller:

```text id="u1"
Win + R
gpmc.msc
```

Navigate to:

```text id="u2"
Forest\Domains\domain.local\Group Policy Objects
```

---

## 2. Create a New GPO

Right-click:

* New

Name:

```text id="u3"
USB Storage Restriction Policy
```

---

## 3. Edit the Policy

Right-click the new GPO:

* Edit

Navigate to:

```text id="u4"
Computer Configuration
 └ Policies
    └ Administrative Templates
       └ System
```

---

## 4. Disable Removable Storage Access

Open:

```text id="u5"
Removable Storage Access
```

Configure the following:

### All Removable Storage Classes: Deny All Access

Set to:

```text id="u6"
Enabled
```

---

## 5. Link the GPO

Right-click the OU:

* Link an Existing GPO
* Select "USB Storage Restriction Policy"

---

## 6. Apply Policy on Client

On Windows 10 client:

```cmd id="u8"
gpupdate /force
```

Then restart or log off.

---

## 7. Verification

After policy applies:

* USB drives will not mount properly
* File Explorer will show restricted access
* Write/read operations will fail

---

## Result

The domain now enforces USB storage restrictions across all targeted machines, improving endpoint security and preventing unauthorized data transfer.
