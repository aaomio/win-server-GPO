# Account Lockout Policy (GPO)

This policy locks user accounts after a defined number of failed login attempts.

It is used to prevent brute-force password attacks in a domain environment.

---

## 1. Open Group Policy Management

On the Domain Controller:

```text id="l1"
Win + R
gpmc.msc
```

---

## 2. Create a New GPO

Navigate to:

```text id="l2"
Forest\Domains\domain.local\Group Policy Objects
```

Right-click:

* New

Name:

```text id="l3"
Account Lockout Policy
```

---

## 3. Edit the Policy

Right-click the GPO:

* Edit

Navigate to:

```text id="l4"
Computer Configuration
 └ Policies
    └ Windows Settings
       └ Security Settings
          └ Account Policies
             └ Account Lockout Policy
```

---

## 4. Configure Lockout Settings

Set the following values:

### Account lockout threshold

```text id="l5"
5 invalid logon attempts
```

---

### Account lockout duration

```text id="l6"
15 minutes
```

---

### Reset account lockout counter after

```text id="l7"
15 minutes
```

---

## 5. Link the GPO

Right-click the target OU:

* Link an Existing GPO
* Select "Account Lockout Policy"

---

## 6. Apply Policy on Client

On Windows 10 client:

```cmd id="l8"
gpupdate /force
```

---

## 7. Test the Policy

Attempt to log in with a domain user:

* Enter wrong password 5 times

Expected result:

* Account gets locked
* User cannot log in temporarily

---

## 8. Verify on Domain Controller

Open:

```text id="l9"
Active Directory Users and Computers
```

Find the user:

* Right-click on user and go to Properties

Check:

* Account is locked out

---

## Result

The domain now enforces account lockout protection after repeated failed login attempts, reducing brute-force attack risk.
