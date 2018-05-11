# Description
The Aperture service started as an open-source, generic, web-based terminal service that I built while at General Electric. The Aperture client is designed to connect to an aperture server, get authorization if this option is added, and create a websocket connection for the purpose of sharing its terminal out to a web interface. This is great for managing devices remotely using a modern, HTML5 interface. The aperture client uses the xterm.js project for terminal emulation.

# Prerequisits
If you are running the server on Windows then you will need to make sure you have the .NET Framework SDK installed. This can be done using the following command:
```
npm install --global --production windows-build-tools
```

# Installation
This application should be able to run on any Windows or Unix machine. Make sure to fill out your .env and then follow these steps:
```
git clone https://github.com/jtviolet/aperture-edge-client.git
cd aperture-edge-client
```

# Configuration
All configuration for the client is stored in `config/config.json`  Here are the environment configurations:
* `interface`: This is the network interface that you want to get your MAC address from which will be used as the unique identifier of your device. E.g. on my raspberry pi the interface is `wlan0`, and my interface for windows is `Wi-Fi`.
* `terminalEnvironment`: This should be set to `bash` if you are running in a Unix environment. If you are running in a Windows environment then it should be `cmd.exe` or `powershell.exe`.
* `terminalName`: This is set to `xterm-256color`. There is no need to change this unless you know what you are doing.
* `terminalColumns`: This is the default number of columns for the terminal, which is set to `80`.
* `terminalRows`: This is the default number of rows for the terminal, which is set to `24`.
* `apertureEndpoint`: This is the URL of your Aperture Server that your device will connect to.

# Usage
```
npm start
```
You will need to have the [aperture-server](https://github.com/jtviolet/aperture-server) running for your device to connect to. The aperture server will also sit and wait for users to connect via a web interface, which I'll be sharing an example in [jtviolet/aperture-client-web](https://github.com/jtviolet/aperture-client-web) soon.

# Contributing
If you feel you can improve this service in any way, I'm happy to accept pull requests for the good of the service. I'm pretty new to Node.js/JavaScript and there is always room for improvement; feel free to submit pull requests.
