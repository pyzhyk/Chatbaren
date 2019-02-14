# [Chatbaren](https://github.com/mrlibertarian/Chatbaren)

[![License](https://img.shields.io/badge/license-GPL-yellow.svg)][license]
![Platform](https://img.shields.io/badge/platform-Linux-blue.svg)
[![Version](https://img.shields.io/badge/version-console-brightgreen.svg)][console-version]

[license]: https://www.gnu.org/licenses/gpl.html
[console-version]: https://github.com/mrlibertarian/Chatbaren

## Secure, open-source, peer-to-peer, end-to-end encrypted [Tor](https://torproject.org/) messaging system for Linux.

## Getting Started

### Dependencies

- [Openssl](https://www.openssl.org/)
- [Tor](https://torproject.org/)
- [Ncat](https://nmap.org/ncat/)
- Shred

#### To install them, run: `apt install openssl tor shred ncat`

### Setup

- Create a symlink to Chatbaren script: `ln -s /path/to/Chatbaren/chatbaren /usr/bin/chatbaren`
- Set Chatbaren folder location: edit `chatbaren` and set `chatbaren_prefix` to `/path/to/Chatbaren`
- Generate your keypair: `chatbaren -g`
- Start Tor hidden service and Ncat server (window to watch messages): `chatbaren -a`
- Open window to send messages: `chatbaren -c address.onion` where address.onion is recipient's Tor hidden service hostname.
- Show your public key: `chatbaren -k` or `cat keys/self/self.pub`
- Show your hostname: `chatbaren -t` or `cat tor/service/hostname`
- To add recipient's public key, add a file in `keys/` folder called `address.onion` containing his key.

 ###### It may take some time to start [Tor hidden service](https://www.torproject.org/docs/onion-services) for a first time.


 [![Console Screenshot 1](https://github.com/mrlibertarian/Chatbaren/blob/master/Images/Screenshot-1.png)](https://github.com/mrlibertarian/Chatbaren/blob/master/Images/Screenshot-1.png)

`chatbaren -c address.onion` (Typing window)

[![Console Screenshot 2](https://github.com/mrlibertarian/Chatbaren/blob/master/Images/Screenshot-2.png)](https://github.com/mrlibertarian/Chatbaren/blob/master/Images/Screenshot-1.png)

`chatbaren -a` (Watching window)

 ##### Happy chatting!

### Qt version: [Chatbaren-Qt](https://github.com/mrlibertarian/Chatbaren-Qt)


### Chat options
- `/NULL` - Hide your username.
- `/FULL` - Show your username.
- `/SUMS` - Display hashsums of your and recipient's public keys.

### Options:
- `-a` - Chat view mode + Server + Tor hidden service in background.
- `-c` address.onion - Type mode to recipient.
- `-o` - Start Tor hidden service.
- `-s` - Xterm chat view window + Server + Tor hidden service.
- `-g` - Wipe old and generate new keypair.
- `-n` - Wipe old and generate new tor address.
- `-k` - Show your public key.
- `-t` - Show your tor address.

### Developer options:
##### (Used for Qt Front-end)
- `-m address.onion msg username` - Send one message to recipient. Localhost sending disabled.
- `-d sums address.onion` - Get address.onion key hashes.
- `-d sums self` - Get your key hashes.
- `-d address` - Get your key hashes.
- `-d prefix` - Get chatbaren_prefix.
- `-d pubkey` - Get your public key.
- `-d username` - Get your username.
- `-d serve` - Start server silently.

### Files and folders:
- `username.txt` - Your username that will be shown in chat window.
- `keys/` - Folder with your recipient's public keys and your keypair.
- `keys/self/self.pub` - Your public key. You may share it clearly to recipients.
- `keys/self/self.key` - Your private key. **DO NOT SHARE IT! NEVER!**
- `tor/chatbaren` - Tor service configuration file.
- `tor/service/hostname` - Your Tor hidden service hostname. Your friend can chat with you only with this name.
- `tor/service/private_key` - Your Tor private key. **DO NOT SHARE IT! NEVER!**

### Log files
- `tor/notices.log` - Tor service notices log.
- `tor/debug.log` - Tor service debug log. It is turned off by default.

## Donation

[![Bitcoin QR-code](Images/Bitcoin-QR.png)](bitcoin:15EmrTsRjFuuiRgohSPKqDjjAXdisWULbs)

**BTC 15EmrTsRjFuuiRgohSPKqDjjAXdisWULbs**
