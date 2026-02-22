# Smart Home Floorplan — Bridge Integration

**Transform your Home Assistant into a visual command center.**

Smart Home Floorplan is a 2D floorplan tool built for Home Assistant. Draw your home, place your devices, and see everything at a glance — lights, temperatures, door states, battery levels, and more — all on an interactive floorplan.

### Why?

I always wanted a nice floorplan view in Home Assistant, but drawing is not my thing — having to build it in Photoshop, SVG editors, or 3D modeling tools made it next to impossible. After many weekends trying to make my dashboard feel more like my house, I ended up building my own tool.

I wanted something that prioritized function and let me read the state of the house at a glance:

- Lights show brightness directly in the room
- Temperature shows as a subtle gradient
- Sensors show their state (e.g. "battery low")
- You can quickly see what's on, off, warm, open, etc.

It's still early, but it works as both a HA panel and a Lovelace card via an add-on.

[Website](https://getsmarthomefloorplan.com) · [Documentation](https://getsmarthomefloorplan.com/docs) · [Demo](https://getsmarthomefloorplan.com/demos) · [Discord](https://discord.gg/ScKGVyaCb7)

---

## What's in This Repo

This repository contains the **Smart Home Floorplan Bridge** — a Home Assistant custom integration that enables the [Lovelace card](https://github.com/loelabs-net/shf-ha-frontend) to communicate with the [Smart Home Floorplan add-on](https://github.com/loelabs-net/shf-ha-addons).

Specifically, the bridge:

- **Proxies requests** between the Lovelace card and the add-on (API and WebSocket)
- **Enables non-admin users** to access the floorplan card on dashboards (without this integration, only admin users can reach the Supervisor API that the card needs)

You need this integration if you want to use floorplan cards on your dashboards. It is **not** needed if you only use the sidebar panel provided by the add-on.

---

## Requirements

- Home Assistant 2023.1 or later
- The [Smart Home Floorplan add-on](https://github.com/loelabs-net/shf-ha-addons) installed and running
- [HACS](https://hacs.xyz/) (recommended for installation)

## Installation

> For the full step-by-step guide with screenshots, see the [Card Installation Docs](https://getsmarthomefloorplan.com/docs/home-assistant/cards).

This integration is typically installed alongside the [frontend card](https://github.com/loelabs-net/shf-ha-frontend). Both are needed for dashboard cards to work.

### Via HACS (Recommended)

1. Install [HACS](https://hacs.xyz/) if you haven't already
2. In HACS, click the **⋮** menu → **Custom repositories**
3. Add the repository:
   - Repository: `https://github.com/loelabs-net/shf-ha-integrations`
   - Type: **Integration**
4. Close the dialog, then search for "Smart Home Floorplan" in HACS
5. Install the integration, then restart Home Assistant
6. Go to **Settings** → **Devices & Services** → **Add Integration** → search for "Smart Home Floorplan" and add it

### Manual Installation

1. Download the latest release from the [releases page](https://github.com/loelabs-net/shf-ha-integrations/releases)
2. Copy the `custom_components/shf_bridge` folder into your Home Assistant `config/custom_components/` directory
3. Restart Home Assistant
4. Add the integration via **Settings** → **Devices & Services**

---

## Related Repositories

Smart Home Floorplan uses three repos for Home Assistant integration:

| Repository | Description |
|---|---|
| **[shf-ha-addons](https://github.com/loelabs-net/shf-ha-addons)** | Supervisor add-on — runs the floorplan service |
| **[shf-ha-frontend](https://github.com/loelabs-net/shf-ha-frontend)** | Lovelace dashboard card for embedding floorplans |
| **[shf-ha-integrations](https://github.com/loelabs-net/shf-ha-integrations)** | This repo — bridge integration for non-admin access |

---

## Support

- Join us on [Discord](https://discord.gg/ScKGVyaCb7) for help, feedback, and discussion
- Email: support@loelabs.net
- [Full Documentation](https://getsmarthomefloorplan.com/docs)

## License

Copyright © 2025 LoeLabs LLC. All rights reserved.

See [Terms of Use](https://getsmarthomefloorplan.com/terms) for details.
