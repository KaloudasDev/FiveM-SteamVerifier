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

If you have any questions or discover a security vulnerability, please contact me directly via my [Discord Profile](https://discordlookup.com/user/1069279857072160921). I am committed to responding promptly and assisting you as quickly as possible.

**Please refrain from publicly disclosing any security vulnerabilities** to ensure proper handling and resolution.

## 📣 Contributing

Contributions are welcome! Please submit a Pull Request (PR) for new features or issues you have resolved, keeping the following guidelines in mind:

* For minor issues such as typographical or grammatical errors, please open an issue rather than a PR.
* Avoid submitting irrelevant, spammy, or troll pull requests.
* Do not attempt to rewrite large portions of the project in a single PR; keep changes focused and manageable.

## 📜 License

This project is licensed under the **MIT License**, granting you full permission to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, under the following conditions:

* You must include the original copyright notice and this permission notice in all copies or substantial portions of the software.
* The software is provided "as is", without warranty of any kind, express or implied.

For full details, see the [MIT License](https://opensource.org/licenses/MIT).

### Created by [KaloudasDev](https://github.com/KaloudasDev)! Please leave a ⭐ if you like this project!
