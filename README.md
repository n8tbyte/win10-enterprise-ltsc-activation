# Windows 10/11 Enterprise LTSC Activation Guide

## Supported Versions

- Windows 11 Enterprise LTSC 2024
- Windows 10 Enterprise LTSC 2021
- Windows 10 Enterprise LTSC 2019

---

## Activation Methods (Choose One)

### Method 1: Automatic (Recommended)

Run `auto-copy.exe` **as Administrator**

Done! If it fails, use Method 2 below.

---

### Method 2: Manual

#### Step 1: Copy Required Files

1. Copy the following folders:
   - `csvlk-pack`
   - `EnterpriseS`

2. Navigate to the destination:
   ```
   C:\Windows\System32\spp\tokens\skus
   ```

3. Paste both folders into that location

#### Step 2: Run Activation Commands

1. Open **Command Prompt (CMD)** as **Administrator**
   - Press `Win + X` → Select "Terminal (Admin)" or "Command Prompt (Admin)"

2. Copy and paste the following commands one by one:

```cmd
cscript.exe %windir%\system32\slmgr.vbs /rilc
cscript.exe %windir%\system32\slmgr.vbs /upk >nul 2>&1
cscript.exe %windir%\system32\slmgr.vbs /ckms >nul 2>&1
cscript.exe %windir%\system32\slmgr.vbs /cpky >nul 2>&1
cscript.exe %windir%\system32\slmgr.vbs /ipk M7XTQ-FN8P6-TTKYV-9D4CC-J462D
cscript.exe %windir%\system32\slmgr.vbs /skms kms.digiboy.ir
cscript.exe %windir%\system32\slmgr.vbs /ato
```

3. Wait for the last command to complete → You'll see an activation confirmation message

---

## Command Reference

| Command | Description |
|---------|-------------|
| `/rilc` | Reinstall licenses and reset installation data |
| `/upk` | Uninstall current product key |
| `/ckms` | Clear previous KMS server settings |
| `/cpky` | Remove product key from Registry (for security) |
| `/ipk` | Install new product key |
| `/skms` | Set KMS server address |
| `/ato` | Activate Windows immediately |

---

## Alternative KMS Servers

If `kms.digiboy.ir` doesn't work, try these alternatives:

```
54.223.212.31
kms.cnlic.com
kms.chinancce.com
kms.ddns.net
franklv.ddns.net
k.zpale.com
m.zpale.com
mvg.zpale.com
kms.shuax.com
kensol263.imwork.net:1688
kms.loli.best
kms.vudy.net
```

**How to change server:**
```cmd
cscript.exe %windir%\system32\slmgr.vbs /skms [server-name]
cscript.exe %windir%\system32\slmgr.vbs /ato
```

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Cannot copy files | Ensure you're running CMD/Explorer as Admin |
| Command errors | Verify CMD is opened as Administrator |
| Activation fails | Try a different KMS server from the list above |
| Missing files | Re-download and verify `csvlk-pack` and `EnterpriseS` folders exist |

---

## Notes

- Internet connection required during activation
- This process is legal for testing and development purposes only
- For commercial use, please purchase a license from Microsoft

---

**Created by:** Community  
**Last Updated:** 2024
