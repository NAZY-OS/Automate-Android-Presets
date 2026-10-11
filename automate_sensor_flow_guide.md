# How to Automatically Enable "Sensors Off" in Automate

This guide explains how to set up the **Automate** app step-by-step to toggle the **Sensors Off** quick settings tile automatically when your Android device boots up.

---

## Prerequisites

1. **Sensors Off Tile Enabled:**
   - Go to **Settings > About Phone** and tap **Build Number** 7 times.
   - Go to **Developer Options > Quick Settings Developer Tiles**.
   - Turn on **Sensors Off**.

2. **Root or ADB Access:**
   - This method requires root permissions for Automate or granted ADB permissions (`android.permission.WRITE_SECURE_SETTINGS`).

---

## Step-by-Step Setup in Automate

### Step 1: Create a New Flow
1. Open the **Automate** app.
2. Tap the **+** (Plus icon) at the bottom right to open a blank editor.

### Step 2: Add the Shell Command Block
1. Tap the **Menu icon** in the top-left corner.
2. Open the **Apps** or **System** category.
3. Drag the **Shell command superuser** block onto the canvas.

### Step 3: Configure the Block
1. Tap the **Shell command superuser** block to open its properties.
2. In the **Command** field, enter this exact command:
   ```bash
   cmd statusbar click-tile com.android.settings/.development.qstile.DevelopmentTiles$SensorsOff
   ```
3. Tap **Save** in the top-right corner.

### Step 4: Connect the Blocks
1. Tap and hold the **OK** dot on the `Flow beginning` block.
2. Drag the line and attach it to the **IN** dot on the `Shell command superuser` block.

### Step 5: Enable Startup Run
1. Tap the **Gear icon** (Flow Properties) at the top of the screen.
2. Check the box for **Run on system startup**.
3. Go back to the main flow screen and tap **Start**.

---

## Testing

- Tap **Start** inside the Automate app to execute the flow manually.
- Check your device's quick settings or status bar to confirm the "Sensors Off" state toggles.
- Reboot your phone to confirm it runs automatically on startup.