# Co-Print 3D Mainsail Theme (unoffical)

I recently upgrade my Creality Ender 3 V3 KE using the Co Print 3D KCM kit (multi-color). It can be purchased here:

[https://coprint3d.com/pages/kcm-klipper-chroma-module](https://coprint3d.com/pages/kcm-klipper-chroma-module)

I rooted my machine and installed Mainsail. I wanted a custom theme so I created this Co Print 3D inspired theme.

## Theme

A custom Mainsail theme tuned for a clean sidebar and a Yellow primary accent color, based on the Co-Print 3D color palette.

- Primary (Accent): **Yellow** `#f6ba1b`
- Green: `#38ab57`
- Red: `#e74736`
- Blue: `#547ebd`

![](https://raw.githubusercontent.com/porrey/Co-Print-3D-Mainsail-Theme/refs/heads/main/src/Screenshot.png)

## What this theme includes

- `custom.css` (theme styling)
- `sidebar-background.jpg`
- `main-background.jpg`
- `favicon-16x16.png`
- `favicon-32x32.png`
- `sidebar-logo.png`

> Mainsail loads custom themes from a hidden folder named `.theme` inside your printer’s `config` directory.

## Install (Git clone)

This is the easiest way to install and update.

### 1) SSH into your printer host

Syntax:

```
ssh <user>@<PRINTER_IP>
```

Example:

```
ssh pi@192.168.1.202
```

### 2) Go to your Mainsail config directory

Most installs use one of these paths:

- `~/printer_data/config`
- `/usr/data/printer_data/config` (common on rooted Creality setups)

```
cd ~/printer_data/config
```
or

```
cd /usr/data/printer_data/config
```
### 3) Clone into `.theme`

```bash
git clone https://github.com/porrey/Co-Print-3D-Mainsail-Theme.git .theme
```
If the above command fails, you may need to install git. Run these two commands and then try again.

a) Update the local packages
```
sudo apt-get update
```

b) Install git
```
sudo apt-get install git -y
```

### 4) Hard refresh your browser

After install/update, do a hard refresh:

- **Windows/Linux:** `Ctrl + Shift + R`
- **macOS:** `Shift + <Rrfresh Button>`

### Update later

```bash
cd ~/printer_data/config/.theme
git pull
```

***Optional***: Enable automatic updates in Mainsail (Update Manager)
Moonraker (which powers Mainsail’s update system) can track your cloned theme repo and offer Update actions in the UI.

1) Open your `moonraker.conf` (typically at *~/printer_data/config/moonraker.conf*).

2) Add this section (adjust the path: if your config directory is different):

```
[update_manager coprint_mainsail_theme]
type: git_repo
path: ~/printer_data/config/.theme
origin: https://github.com/porrey/Co-Print-3D-Mainsail-Theme.git
primary_branch: main
managed_services:
```

> Notes: - path must point to the folder that contains the .git directory (your cloned .theme). - If your host uses /usr/data/printer_data/config, then set: - path: /usr/data/printer_data/config/.theme - managed_services can be left blank for a theme (no service to restart).

3) Save `moonraker.conf`, then restart Moonraker (or reboot the host). After that, you should see a new entry in Settings → Update Manager.

## Install (Manual)

### 1) Create the `.theme` folder

In Mainsail:

1. Go to **Machine → Files**
2. Open the **config** directory
3. Enable **Show hidden files** (gear icon)
4. Create a folder named: **`.theme`**

### 2) Upload all files `custom.css`

Upload the files listed:

- `config/.theme/custom.css` (theme styling)
- `config/.theme/sidebar-background.jpg`
- `config/.theme/main-background.jpg`
- `config/.theme/favicon-16x16.png`
- `config/.theme/favicon-32x32.png`
- `config/.theme/sidebar-logo.png`

### 3) Hard refresh your browser

- **Windows/Linux:** `Ctrl + Shift + R`
- **macOS:** `Cmd + Shift + R`


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
