# JSMTProxy
[![Telegram Channel](https://img.shields.io/badge/Channel-Telegram-blue.svg)](https://t.me/JSMTProxy)

High Performance NodeJS MTProto Proxy

### Latest Active MTProto Proxies: https://t.me/MTProxy

## Linux Installation

Install NodeJS, NPM, GIT and PM2 on your server:

### Debian & Ubuntu
```
apt-get install nodejs npm git
npm install pm2 -g
```

### CentsOS & RHEL
```
yum install nodejs npm git
npm install pm2 -g
```

Check the version of NodeJS, it should be version 6 or higher:
```
nodejs -v
# v6.14.2
```
If it is lower than 6, you need to upgrade your linux OS or install nodejs from its website:
https://nodejs.org/en/download/

Clone repository on your server:
```
git clone https://github.com/bezzad/JSMTProxy.git
```

Enter JSMTProxy directory and edit config file (config.json) if you wish. You can change the secret and listening port. it is in json format.
```
{
  "port":8008,
  "secret":"beeaadf5a486d9636472ac27f8beeaad"
}
```

Start the app in cluster mode using pm2:

```pm2 start mtproxy.js -i max```

You can use pm2 to list running processes and check their logs:
```
pm2 list
pm2 log mtproxy
pm2 show mtproxy
```

Suppose your pm2 is running having some processes. First, you need to save the processes.

```pm2 save```

Next, you need to run the pm2 in startup. So if system rebooted your pm2 automatically started with processes.

```pm2 startup```

## Windows Installation

Download and install NodeJS for Windows using this link: https://nodejs.org/dist/v8.11.2/node-v8.11.2-x64.msi

After installation is complete, enter "Command Prompt" and install PM2 by following command:
```
npm install pm2 -g
```

Download JSMTProxy using this link: https://github.com/FreedomPrevails/JSMTProxy/archive/master.zip

Extract the zip file into a new folder. Edit config.json (as explained above) if you wish to change port number or secret.

Start the proxy server from "Command Prompt" by following command:
```
pm2 start mtproxy.js -i max
```

> Note: You may need to open the proxy port number in your Windows firewall in order for it to accept connections.
