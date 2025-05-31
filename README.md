# 🛡️ Steam Verifier

**Steam Verifier** is an open-source FiveM server script that enforces Steam authentication by preventing players from connecting without an active Steam client. Leveraging the `playerConnecting` event, it ensures a secure and reliable connection environment for your server, verifying that all users are properly authenticated through Steam Client.

---

## ✨ Features

| ✅  | Description                                           |
| -- | ----------------------------------------------------- |
| ✔️ | Checks if the player has an active Steam connection   |
| ✔️ | Denies connection to players without Steam running    |
| ✔️ | Fully compatible with `playerConnecting` deferrals    |
| ✔️ | Handles invalid connections (e.g. `src == nil`)       |
| ✔️ | Clean and clear kick messages (`deferrals.done(...)`) |
| ✔️ | Easy integration with any FiveM server                |
| ✔️ | Minimal resource usage with zero performance impact   |


> \[!TIP]
> Steam client **must be running before launching FiveM**, otherwise the player will be rejected.

---

## 🔧 How It Works

The script hooks into the `playerConnecting` event and inspects the player’s identifiers for a valid `steam:` ID. If none is found, the connection is rejected.

This solution requires no databases or complex authentication logic, providing a simple yet effective enforcement of Steam-only connections.

```lua
AddEventHandler('playerConnecting', function(name, setKickReason, deferrals)
    -- Full code available in `steamCheck.lua`
end)
```

---

## 📦 Installation

1. Download or copy the `steamCheck.lua` file.
2. Place it inside a resource folder, e.g. `/resources/[local]/steam-verifier/`.
3. Add the following to the resource’s `fxmanifest.lua` file:

```lua
fx_version 'cerulean'
game 'gta5'

author 'Kaloudas'
description 'Resource that kicks players without active Steam client'
version '1.0.0'

server_script 'steamCheck.lua'
```


> \[!WARNING]
> This script requires a valid Steam Web API Key to properly verify player Steam IDs.
> Make sure to configure your Steam Web API Key in the script before use.

4. Enable the resource in your `server.cfg`:

```cfg
ensure steam-verifier
```


> \[!CAUTION]
> Temporary Steam connectivity issues may require restarting Steam and FiveM.

---

## ⚠️ Example Kick Message

```
Connection denied. Steam must be running to join this server.
```
