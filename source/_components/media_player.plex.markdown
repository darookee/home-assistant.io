---
layout: page
title: "Plex"
description: "Instructions how to integrate Plex into Home Assistant."
date: 2015-10-05 21:21
sidebar: true
comments: false
sharing: true
footer: true
logo: plex.png
ha_category: Media Player
featured: true
ha_release: 0.7.4
---


The `plex` platform allows you to connect a [Plex Media Server](https://plex.tv) to Home Assistant. It will allow you to control media playback and see the current playing item. The preferred way to setup the Plex platform is by enabling the the [the discovery component](/components/discovery/) and requires GDM to be enabled.

If local authentication is enabled or multiple users are defined, HASS requires an authentication token to be entered in the webinterface. See [Finding your account token / X-Plex-Token](https://support.plex.tv/hc/en-us/articles/204059436).

If you want to enable the plex platform directly, add the following lines to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
media_player:
  platform: plex
```

In case discovery does not work (GDM disabled or non-local plex server), you can create `~/.homeassistant/plex.conf` manually.

```json
{"IP_ADDRESS:PORT": {"token": "TOKEN"}}
```

- **IP_ADDRESS** (*Required*): IP address of the Plex Media Server
- **PORT** (*Required*): Port where Plex is listening. Default is 32400
- **TOKEN** (*Optional*): Only if authentication is required. Set to `null` (without quotes) otherwise.

At this moment, the Plex platform only supports one Plex Media Server.
