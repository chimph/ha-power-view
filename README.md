# 🔋 Custom Power UI

Ready-to-use Home Assistant dashboard view with pre-configured dummy sensors that simulate solar, battery, and home energy usage. See the complete UI without any hardware setup or configuration needed. Just import and customise as desired.

![Screenshot 2025-04-10 212332](https://github.com/user-attachments/assets/c93f5dec-0068-4fbe-a487-074caa173694)

---

## 📦 Prerequisites (via HACS)

Make sure you have the following custom cards installed via [HACS](https://hacs.xyz/):

- [Vertical Stack In Card](https://github.com/ofekashery/vertical-stack-in-card)
- [card-mod](https://github.com/thomasloven/lovelace-card-mod)
- [Sankey Chart Card](https://github.com/MindFreeze/ha-sankey-chart)

---

## ➡️ Installation – View in Your Own Dashboard

### 1. Create Folder

Create a `lovehub` folder in your Home Assistant top-level directory, and add the `ha-power-view-main` folder which contains the dummy sensor files.

```plaintext
homeassistant/
├── lovehub/
│   └── ha-power-view-main/
│       ├── power_ui_view.yaml
│       ├── README.md
│       └── sensors.yaml
```

> this may go under a `/config` folder when HA is installed as OS or in a container rather than Core

---

### 2. Include It in `configuration.yaml`

Edit Home Assistant's `configuration.yaml` file to load the demo package:

```yaml
homeassistant:
  packages: !include_dir_named lovehub
```

---

### 3. Add the Dashboard View

Click **Edit Dashboard** → **Add View** → **Three-dot menu** → **Edit YAML**.

![Screenshot 2025-04-11 081635](https://github.com/user-attachments/assets/c835a5b4-4528-4e80-b9d8-4f4cd298db8e)

Then paste in the contents of `power_ui_view.yaml`.

---

### 4. Restart Home Assistant

Restart Home Assistant to apply the changes.

---

### 5. Change it up

Change numbers (states) via Developer Tools > States or edit sensors.yaml.

> States will reset to whatever is hardcoded in the sensors.yaml anytime you restart HA

Muck about with the CSS to put your own flavour on it.

> Conditional solar is importing when positive and exporting when negative (card not shown when zero)
>
> Conditional battery is exporting when negative and importing when positive (card not shown when zero)
> 
>![Screenshot 2025-04-11 075336](https://github.com/user-attachments/assets/ac3899a8-1298-45a0-9742-bccbdc05caa0)

---

### 6. ✅ Done

Enjoy your simulated energy dashboard!
