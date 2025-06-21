# error-0x87e000C8 (Using external drive to download apps/games from MS Store)

The drive won’t appear as a valid install location under Storage settings or inside the Store/Xbox App.

---

## 💡 The Fix
This shockingly simple fix solved everything for me — without needing advanced hacks or risky tweaks.

### ✅ Steps:
1. Plug in your external SSD (mine was Crucial BX500 via USB 3.0 enclosure)
2. Right-click the drive → **Properties**
3. Go to **Sharing** tab → click **Advanced Sharing**
4. ✅ Check “Share this folder”
5. Click **Permissions** → select **Everyone** → enable **Full Control**
6. Hit OK / Apply, close the dialog.
7. Open Xbox App or Microsoft Store. Your drive will now appear as a valid installation option.

🎮 I tested it by installing Minecraft and it downloaded without any errors or complaints.

---

## 🧪 Tested On:
- Windows 11 Home
- Crucial BX500 480GB SSD (external)
- Microsoft Store + Xbox App
- Game tested: Minecraft (Game Pass)

---

## 📸 Screenshots:
See [`/images`](images) folder for proof and configurations:
![Step 1 – Storage Settings](images/step1-settings.png)
![Step 2 – Sharing Settings](images/step2-settings.png)
![Step 3 – Success Screen](images/step3-settings.png)

---

## 🧠 Why This Works (The Tech Behind It)

Even if your external SSD is properly formatted (e.g., NTFS), Windows apps like the Microsoft Store or Xbox App may still reject it due to strict permissions checks.

These apps often run in a sandboxed environment and expect install drives to have:
- Writable access
- Trusted share-level permissions

When you **share the drive with full control for “Everyone”**, you essentially unlock that missing permission layer. It tricks the system into treating your drive like a trusted, writable install path — even for sandboxed apps.

---

## 🔧 What Microsoft Could Do

To avoid this bug entirely, Microsoft could:
- Relax install restrictions for non-removable NTFS drives
- Show better error messages (like “Try sharing this folder to enable access”)
- Provide a fix via Xbox or Store app updates

---

## 🙋‍♂️ Who Am I?
I'm **Arpan**, a 16 y/o student who likes breaking and fixing things. I’m self-taught, curious, and love solving weird tech issues.  
If anyone at Microsoft (or anywhere cool) is reading this — I’d *love* an internship opportunity someday 👀

---

## 🧠 Why This Works (Probably):
The Microsoft Store and Xbox App use internal permission checks that reject drives without proper network/share access.  
By granting shared access via SMB (even locally), the Store likely whitelists the drive as installable.

---

## 🪪 License
MIT License – see [`LICENSE`](./LICENSE) for details.  
Use it freely, modify it, share it — just don’t sue me 😅  
Attribution appreciated but not required 💜
