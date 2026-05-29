# Interactive Logon Message (GPO)

This policy displays a security and usage message before users sign in to the domain.

It is used to remind users about proper usage and automatic sign-out expectations.

---

## 1. Open Group Policy Management

On the Domain Controller:

```text id="g1"
Win + R
gpmc.msc
```

Navigate to:

```text id="g2"
Forest\Domainss\domain.local\Group Policy Objects
```

---

## 2. Create a New GPO

Right-click:

* New

Name:

```text id="g3"
Session Sign-Out Warning Policy
```

---

## 3. Edit the Policy

Right-click the new GPO:

* Edit

Navigate to:

```text id="g4"
Computer Configuration
 └ Policies
    └ Windows Settings
       └ Security Settings
          └ Local Policies
             └ Security Options
```

---

## 4. Configure Logon Message

### Message Title

```text id="g5"
Interactive logon: Message title for users attempting to log on
```

Set value:

```text id="g6"
Session Notice
```

---

### Message Text

```text id="g7"
Interactive logon: Message text for users attempting to log on
```

Set value:

```text id="g8"
This system is for authorised use only.

Please sign out when you are finished using the system.
Failure to do so may result in session termination or account restriction.
```

---

## 5. Link the GPO

Right-click the OU:

* Link an Existing GPO
* Select "Session Sign-Out Warning Policy"

---

## 6. Apply Policy on Client

On Windows 10 client:

```cmd id="g9"
gpupdate /force
```

Restart or sign out.

---

## 7. Verification

When a user logs in, they will see:

* A pre-logon warning message
* Sign-out reminder

---

## Result

The domain now enforces a logon banner reminding users to properly sign out after use.
