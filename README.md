# 🛡️ Steam Verifier
**Steam Verifier** is an open-source FiveM server script that enforces Steam authentication by preventing players from connecting without an active Steam client. Leveraging the `playerConnecting` event, it ensures a secure and reliable connection environment for your server, verifying that all users are properly authenticated through Steam Client.

Perfect for roleplay servers, whitelist groups, and online communities!

## ✨ Features
- [x] Checks if the player has an active Steam connection
- [x] Denies connection to players without Steam running
- [x] Fully compatible with `playerConnecting` deferrals
- [x] Handles invalid connections (e.g. `src == nil`)
- [x] Clean and clear kick messages (`deferrals.done(...)`)
- [x] Easy integration with any FiveM server
- [x] Minimal resource usage with zero performance impact
- [ ] More features to come in the future...

## ⚙️ How it works
The script hooks into the `playerConnecting` event and inspects the player’s identifiers for a valid `steam:` ID. If none is found, the connection is rejected.

This solution requires no databases or complex authentication logic, providing a simple yet effective enforcement of Steam-only connections.

```lua
AddEventHandler('playerConnecting', function(name, setKickReason, deferrals)
    -- Full code available in `steamCheck.lua`
end)
```

## 🛠️ Installation
1. Download or copy the `steamCheck.lua` file.
2. Place it inside a resource folder, e.g. `/resources/[local]/steam-verifier/`.
3. Add the following to the resource’s `fxmanifest.lua` file:

```lua
fx_version 'cerulean'
game 'gta5'
version '1.0.0'

server_script 'steamCheck.lua'
```
> \[!WARNING]
> This script requires a valid Steam Web API Key to properly verify player Steam IDs.
> Make sure to configure your Steam Web API Key in the script before use.

```cfg
set steam_webApiKey "YOUR_STEAM_WEB_API_KEY"
```

4. Enable the resource in your `server.cfg`:

```cfg
ensure steam-verifier
```


> \[!CAUTION]
> Temporary Steam connectivity issues may require restarting Steam and FiveM.

## 🔎 Support & Security
If you have any questions or if you discover a security vulnerability within Cially, please join my [Discord Server](https://discord.gg/TNzPwhRvXH) and let me know! I will try to assist you as soon as possible!
Please do not publish publicly security vulnerabilities. 

## 📣 Contributing
Please open a PR for new features or issues you managed to fix! However keep the following in mind:
- Do not open pull requests regarding minor issues such as grammatical errors. Open an issue instead.
- Do not sumbit "troll" or "spam" requests.
- Do not rewrite a big part of the project in a single pull request.

## 📜 License
This project is licensed under the [Attribution-NonCommercial-NoDerivs 2.0 License](https://creativecommons.org/licenses/by-nc-nd/2.0/deed.en)
### You are free to:
- **Share** — copy and redistribute the material in any medium or format.
- **Adapt** — remix, transform, and build upon the material.
The licensor cannot revoke these freedoms as long as you follow the license terms.
### Under the following terms:
- **Attribution** — You must give appropriate credit , provide a link to the license, and indicate if changes were made . You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **NonCommercial** — You may not use the material for commercial purposes .
-** No additional restrictions** — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

### Created by [KaloudasDev](https://github.com/KaloudasDev)! Please leave a ⭐ if you like this project!
