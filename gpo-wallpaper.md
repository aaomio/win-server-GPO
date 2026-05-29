# Desktop Wallpaper Deployment (GPO)

This policy applies a standard desktop wallpaper to domain users.

It is commonly used to enforce corporate branding and provide a consistent desktop experience.

---

## 1. Prepare Wallpaper

On the Domain Controller create a folder:

```text
C:\Wallpapers
```

Copy the  wallpaper image into the folder.

Example:

```text
C:\Wallpapers\matrix-wallpaper.jpg
```

---

## 2. Share the Folder

Right-click:

```text
C:\Wallpapers
```

Select:

```text
Properties\Sharing\Advanced Sharing
```

Enable:

```text
Share this folder
```

Example share name:

```text
Wallpapers
```

Grant:

```text
Authenticated Users
```

Read permissions.

---

## 3. Verify Network Access

From the Windows 10 client open:

```text
\\DC01\Wallpapers
```

Replace **DC01** with Domain Controller hostname.

Verify the wallpaper image is accessible.

---

## 4. Create a New GPO

Open:

```text
Win + R
gpmc.msc
```

Navigate to:

```text
Forest\Domains\matrix.local\Group Policy Objects
```

Create a new GPO:

```text
Wallpaper Policy
```

---

## 5. Configure Wallpaper Settings

Edit the GPO and navigate to:

```text
User Configuration
 └ Policies
    └ Administrative Templates
       └ Desktop
          └ Desktop
```

Open:

```text
Desktop Wallpaper
```

Set:

```text
Enabled
```

Wallpaper Name:

```text
\\DC01\Wallpapers\matrix-wallpaper.jpg
```

Wallpaper Style:

```text
Fill
```

---

## 6. Link the GPO

Link the GPO to the OU containing users.

Example:

```text
Users
```

---

## 7. Apply the Policy

On the Windows 10 client:

```cmd
gpupdate /force
```

Sign out and sign back in.

---

## 8. Verification

After login:

* Desktop wallpaper should automatically change
* Users should not need to manually configure the background

---

## Result

Domain users receive a centrally managed desktop wallpaper through Group Policy.
