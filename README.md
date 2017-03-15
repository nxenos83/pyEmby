# Introduction

This is a python module aiming to interact with the Emby Media Server (http://emby.media) api.

Code is licensed under the MIT license.

# Version Change

Version 1.0 utilizes python's asyncio module to perform communication with the emby server over websockets and http.  Polling is no longer required to recieve device updates and many callback options are available.

Version 0.2 and below utilized the requests library and provided a simplistic interface to the emby api.

If you do not wish to incorporate the new ayncio platform please utilize Version 0.2 via it's git tag or as found in the "original" branch on this repository.

# Requirements
Mostly standard libraries are used:
* json
* uuid
* asyncio
* aiohttp
* async_timeout

# Installation

```pip install pyemby```


Getting Started
===============

# In Use

This library was created primarily for use with Home-Assistant.  The source code for the "Emby" media_player component is a full example of library usage.

# Basic Example

```python
import pyemby.emby

Emby = pyemby.emby.EmbyRemote('api_key', 'http://192.168.1.5:8096')

from pyemby import EmbyServer

emby = EmbyServer(host, api_key, port=8096, ssl=False, loop=None)

emby.add_new_devices_callback(device_update_callback)

emby.add_stale_devices_callback(device_removal_callback)


emby.start()

```

