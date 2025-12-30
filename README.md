# Co-Print-3D Mainsail Theme

A custom Mainsail theme tuned for a clean sidebar and a Yellow primary accent color, based on the Co-Print 3D color palette.

- Primary (Accent): **Yellow** `#f6ba1b`
- Green: `#38ab57`
- Red: `#e74736`
- Blue: `#547ebd`
## What this theme includes
- `custom.css` (theme styling)
- Background images:
  - `sidebar-background.jpg`
  - `main-background.jpg`
  - `favicon-16x16.png`
  - `favicon-32x32.png`
  - `sidebar-logo.png`

---
> Mainsail loads custom themes from a hidden folder named `.theme` inside your printer’s `config` directory.

---
## Install (Git clone)
This is the easiest way to install and update.
### 1) SSH into your printer host
Example:
```bash
ssh pi@<PRINTER_IP>
```
### 2) Go to your Mainsail config directory
Most installs use one of these paths:

- `~/printer_data/config`
- `/usr/data/printer_data/config` (common on rooted Creality/KE setups)

```bash
cd ~/printer_data/config
# or
cd /usr/data/printer_data/config
```
### 3) Clone into `.theme`
```bash
git clone https://github.com/porrey/Co-Print-3D-Mainsail-Theme.git .theme
```
### 4) Hard refresh your browser
After install/update, do a hard refresh:
- **Windows/Linux:** `Ctrl + Shift + R`
- **macOS:** `Cmd + Shift + R`
### Update later
```bash
cd ~/printer_data/config/.theme
git pull
```

Optional: Enable automatic updates in Mainsail (Update Manager)
Moonraker (which powers Mainsail’s update system) can track your cloned theme repo and offer Update actions in the UI.

1) Open your moonraker.conf (typically at ~/printer_data/config/moonraker.conf).

2) Add this section (adjust the path: if your config directory is different):

[update_manager coprint_mainsail_theme]
type: git_repo
path: ~/printer_data/config/.theme
origin: https://github.com/porrey/Co-Print-3D-Mainsail-Theme.git
primary_branch: main
managed_services:
Notes: - path must point to the folder that contains the .git directory (your cloned .theme). - If your host uses /usr/data/printer_data/config, then set: - path: /usr/data/printer_data/config/.theme - managed_services can be left blank for a theme (no service to restart).

3) Save moonraker.conf, then restart Moonraker (or reboot the host). After that, you should see a new entry in Settings → Update Manager.
## Install (Manual)

### 1) Create the `.theme` folder
In Mainsail:
1. Go to **Machine → Files**
2. Open the **config** directory
3. Enable **Show hidden files** (gear icon)
4. Create a folder named: **`.theme`**

### 2) Upload `custom.css`
Upload `custom.css` into:
- `config/.theme/custom.css`

### 3) (Optional) Upload sidebar background images
Upload these (if you want sidebar backgrounds):
- `sidebar-background-expanded.jpg`
- `sidebar-background-mini.jpg`

Place them here:
- `config/.theme/sidebar-background-expanded.jpg`
- `config/.theme/sidebar-background-mini.jpg`

> Note: Sidebar images are optional. The theme works without them.

### 4) Hard refresh your browser
- **Windows/Linux:** `Ctrl + Shift + R`
- **macOS:** `Cmd + Shift + R`

## Optional: Enable sidebar background images

The `custom.css` includes an **optional** section at the bottom for sidebar background images.
To enable it:
1. Open `config/.theme/custom.css`
2. Find the section labeled:
   `OPTIONAL: Sidebar background images (force, full-height)`
3. Uncomment that block (remove the surrounding `/* ... */` comment markers)
4. Hard refresh your browser

## Troubleshooting

### My changes don’t show up
- Do a hard refresh (`Ctrl/Cmd + Shift + R`)
- Clear your browser cache (if needed)
- Confirm the file is exactly:
  - `config/.theme/custom.css`

### I can’t find `.theme`
`.theme` is a hidden folder. In Mainsail file manager, enable **Show hidden files**.

## License

MIT License — see the header in `custom.css`.
