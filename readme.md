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

### 👥 Core Clan Commands

/clan  
→ Shows your clan information

/clan create <tag> <description>  
→ Create a new clan

/clan leave  
→ Leave your current clan

/clan disband forever  
→ Disband your clan (owner only)


#### 📩 Invites

/clan invite <player>  
→ Invite a player to your clan

/clan withdraw <player>  
→ Withdraw a pending invite

/clan accept <tag>  
→ Accept a clan invite

/clan reject <tag>  
→ Reject a clan invite


#### ⚔️ Management

/clan kick <player>  
→ Kick a member from the clan

/clan promote <player>  
→ Promote a member (owner only)

/clan demote <player>  
→ Demote a member (owner only)


#### 🎨 Customization

/clan tagcolor <hex>  
→ Set clan tag color (if enabled)

/clan tagcolor reset  
→ Reset clan tag color to default


---

### 💬 Chat Commands

/c <message>  
→ Send a message to clan chat

/a <message>  
→ Send a message to alliance chat


---

### 📘 Info & Help

/clanhelp  
→ Displays all available clan commands

/cinfo <tag>  
→ View detailed information about a clan


---

### 🤝 Alliance Commands

/ally invite <tag>  
→ Send an alliance request to another clan

/ally withdraw <tag>  
→ Withdraw a sent alliance request

/ally accept <tag>  
→ Accept an alliance request

/ally reject <tag>  
→ Reject an alliance request

/ally revoke <tag>  
→ Remove an existing alliance

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
