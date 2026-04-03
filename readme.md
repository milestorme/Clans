# 🌩 RustStorm Clans (Wipe-Ready Edition)

Enhanced version of the classic **Clans** plugin by k1lly0u, updated for modern Rust servers with optional **automatic clan wipes on server wipe**.

---

## ✨ Features

* ✅ Full clan system (create, invite, promote, alliances)
* 💬 Clan & alliance chat channels
* 🎨 BetterChat tag integration
* ⚔️ Member roles (Owner / Moderator / Member)
* 🤝 Clan alliances system
* 🧹 Automatic inactive clan purging
* 💾 Persistent data system

### 🆕 RustStorm Enhancements

* 🔥 **Auto Clan Wipe Support**

  * Optionally wipes ALL clans on map wipe
  * Prevents stale clan dominance across wipes
  * Safe: only triggers once per wipe

---

## ⚙️ Installation

1. Place the plugin in:

   ```
   /oxide/plugins/Clans.cs
   ```

2. Start or reload:

   ```
   oxide.reload Clans
   ```

3. Edit config:

   ```
   /oxide/config/Clans.json
   ```

---

## 🔧 Configuration

### New Wipe Option

```json
"Settings": {
  "Log clan and member changes": false,
  "Data save interval (seconds)": 900,
  "Wipe clans on server wipe (Rust only)": true
}
```

### What it does:

* `true` → wipes all clans when server map wipes
* `false` → keeps clans across wipes (default behavior)

---

## 🔄 How Wipe Detection Works

* Uses Rust hook: `OnNewSave`
* Detects new map save (wipe)
* Tracks last wipe internally to avoid duplicate resets
* Fully clears:

  * Clan data
  * Member mappings
  * Invites

---

## 📜 Commands

### Player Commands

```
/clan create <tag> <description>
/clan invite <player>
/clan accept <tag>
/clan leave
/clan kick <player>
/clan promote <player>
/clan demote <player>
/clan disband forever
/clanhelp
```

### Chat Channels

```
/c <message>      → Clan chat
/a <message>      → Alliance chat
```

---

## 🔌 Compatibility

* ✅ Works with **BetterChat** (for clan tags)
* ✅ Works with most PvP / event plugins
* ⚠️ Requires Oxide/uMod

---

## 🧠 Notes

* Clan data is stored in:

  ```
  /oxide/data/clan_data.json
  ```
* Wipe option will **delete this data automatically** on wipe
* Purge system still applies for inactive clans if wipe is disabled

---

## ⚠️ Important

* Enabling wipe mode is **NOT reversible**
* All clans will be permanently deleted on wipe
* Recommended for:

  * Competitive servers
  * Monthly wipe cycles
  * Vanilla+ balance

---

## 🛠 Credits

* Original plugin: **k1lly0u**
* Modifications & wipe system: **Milestorme**

---

## 🌩 RustStorm

Built for performance, balance, and clean wipe cycles.

---
