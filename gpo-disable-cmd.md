 Command Prompt Restriction (GPO)

This policy prevents users from accessing the Windows Command Prompt.

It is commonly used to reduce unauthorized system administration and prevent the execution of command-line tools by standard users.

---

## 1. Open Group Policy Management

On the Domain Controller:

```text
Win + R
gpmc.msc
```

Navigate to:

```text
Forest\Domains\matrix.local\Group Policy Objects
```

---

## 2. Create a New GPO

Right-click:

```text
Group Policy Objects
```

Select:

```text
New
```

Name the policy:

```text
Command Prompt Restriction Policy
```

---

## 3. Edit the Policy

Right-click the newly created GPO and select:

```text
Edit
```

Navigate to:

```text
User Configuration
 └ Policies
    └ Administrative Templates
       └ System
```

---

## 4. Configure Command Prompt Restriction

Open:

```text
Prevent access to the command prompt
```

Set:

```text
Enabled
```

When prompted:

```text
Disable the command prompt script processing?
```

Select:

```text
Yes
```

This prevents users from:

* Opening Command Prompt
* Running batch files
* Executing command-line scripts

---

## 5. Link the GPO

Link the policy to the OU containing users.

Example:

```text
Users
```

---

## 6. Apply the Policy

On the Windows 10 client:

```cmd
gpupdate /force
```

Sign out and sign back in.

---

## 7. Verification

Press:

```text
Win + R
```

Type:

```text
cmd
```

Expected result:

```text
The command prompt has been disabled by the administrator.
```

---

## Result

The domain now prevents users from accessing Command Prompt through a centrally managed Group Policy Object.
