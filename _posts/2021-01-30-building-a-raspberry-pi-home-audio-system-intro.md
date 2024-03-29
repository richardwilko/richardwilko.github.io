---
published: false
gallery:
  - url: /assets/images/current-system/current-1-th.jpg
    image_path: /assets/images/current-system/current-1.jpg
    alt: "Current Hub 1"
    title: "Current Hub 1"
  - url: /assets/images/current-system/current-2-th.jpg
    image_path: /assets/images/current-system/current-2.jpg
    alt: "Current Hub 2"
    title: "Current Hub 2"
  - url: /assets/images/current-system/current-3-th.jpg
    image_path: /assets/images/current-system/current-3.jpg
    alt: "RCA"
    title: "RCA"
  - url: /assets/images/current-system/current-4-th.jpg
    image_path: /assets/images/current-system/current-4.jpg
    alt: "Control Pad"
    title: "Control Pad"
categories:
  - Raspberry Pi
tags:
  - Raspberry Pi
  - multiroom
---
## Building a Raspberry Pi powered home audio system

I recently moved into a house with a hardwired multiroom home audio system from SystemLine.  The system is both non-functioning, and obsolete, dating from 2005.  Therefore, unlike other Raspberry Pi multiroom systems, I am not starting from scratch, and I want to use as much of the existing system as possible.  

### Existing System:
- Master bedroom: 2 passive wall mounted speakers, wall mounted touchscreen control unit, wall socket RCA input/output unit.
- Bathroom: ceiling  mounted 'active' speaker unit.
- Living room: 4 passive speaker plug sockets ('banana plugs') wired in series for left and right, touchscreen control pad and wall socket RCA.
- Kitchen: same as master bedroom.
- Garden: speaker cables - i've only found one so far, with a small control pad just inside the door.

The speakers (and speaker sockets) are wired to a central hub location via standard audio cable.

The RCA plugs were designed to run line-level audio signal from the TV, over the cat5, and into the hub, essentially so you can get the TV sound to output from the wall-mounted speakers.  I don't think I will be making use of them, since I have a modern 5.1 surround sound system for the living room, and I am fine with the TV speakers in other rooms.  However I may be able to make use of the ethernet cable behind them.

The touch screen control units are also wired via cat5, and are powered using PoE.  However these are custom SystemLine units, and not generally reusable.  I will likely replace them with a custom Pi-Powered touchscreen system, connected and powered over ethernet.

#### Existing Audio hardware:
- 2 Harman Kardon TU-970 DAB digital radio receivers.
  - The central hub would control these via Infra-Red.
- 1 Harman Kardon DVD player - I think for playing CDs.
  - The central hub would control this via Infra-Red too, though you would have to change the CD manually.
- 1 Old school iPod dock in the Kitchen
- 4 SystemLine 'zone amplifier', one for each passive zone.
- 2 SystemLine control unit things.

{% include gallery layout="half" caption="Current System" %}

### The plan

I want to make use of the existing speakers and cabling, but replace the obsolete hardware with something that can cope with today's digital audio options.

#### General requirements:
- Each zone must be able to play music from, in order of importance
  1. Spotify.
  1. Internet Radio (e.g. via TuneIn or saved playlist).
  1. Phone via Bluetooth.
  1. FLAC files on NAS.
  1. Podcasts.
  1. Chromecast for audio
- Must be easy to control
  - For example, for Spotify, it must support [Spotify connect](https://www.spotify.com/us/connect/), and 'just work'.
  - No complex menu hierarchies.
  - Note, I can live with the multiroom aspect being a bit more complex to set up, as this wont be required every day.
- The system must be stable.
- The system must not sound crappy.
