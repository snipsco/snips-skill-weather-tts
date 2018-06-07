# Snips Weather TTS action
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/snipsco/snips-skill-owm/master/LICENSE.txt)

This is a Snips weather action written in Python and is compatible with `snips-skill-server`.
It is meant to be used as a demo in the `snips-platform-demo` package.
This action subscribes to all intents and only parses the weather intents. The result is then spoken through TTS.

This action won't give you a weather result, check [snips-skill-owm](https://github.com/snipsco/snips-skill-owm) for this.

## Setup with APT

The APT package contains the weather assistant and the action.
The assistant will be placed in `/usr/share/snips/assistant` and the action in `/var/lib/snips/skill/snips-skill-weather-tts`
The virtual environment will also be created for you and the `snips-skill-server` will be restarted.

`sudo apt-get install snips-platform-demo`


## Setup without APT
### Prerequisites

You'll need to add the Weather english skill in your assistant. It's available on [Snips' console](https://console.snips.ai)

### SAM (preferred)
To install the action on your device, you can use [Sam](https://snips.gitbook.io/getting-started/installation)

`sam install action -g https://github.com/snipsco/snips-skill-weather-tts.git`

### Manually

Copy it manually to the device to the folder `/var/lib/snips/skills/`
You'll need `snips-skill-server` installed on the pi

`sudo apt-get install snips-skill-server`

Stop snips-skill-server & generate the virtual environment
```
sudo systemctl stop snips-skill-server
cd /var/lib/snips/skills/snips-skill-weather-tts/
sh setup.sh
sudo systemctl start snips-skill-server
```

## How to trigger

`Hey Snips`

`What will be the weather in London in two days?`

## Logs
Show snips-skill-server logs with sam:

`sam service log snips-skill-server`

Or on the device:

`journalctl -f -u snips-skill-server`

Check general platform logs:

`sam watch`

Or on the device:

`snips-watch`
