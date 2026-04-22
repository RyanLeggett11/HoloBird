# HoloBird: Open-Source Holographic Bird Deterrent

A weather-resistant, autonomous 3D holographic projection system designed to prevent bird habituation through dynamic predatory behavioral simulations.


## Project Overview

HoloBird is an optical holographic deterrent developed to protect outdoor areas from nuisance birds. Unlike static decoys, HoloBird uses a Raspberry Pi 5 to project high-definition, high-frame-rate videos of birds onto a custom-built plexiglass prism.

The system creates a “3D” effect visible from four directions, simulating realistic behaviors like preening and head-turning. The unit is housed in a weatherproof “black box” enclosure designed for autonomous, set-and-forget operation in outdoor environments.


## Current State (Final Prototype)

The project is fully functional and has completed environmental and operational testing.

* **Autonomous Operation:** Video sequence starts in under 25 seconds via systemd and can be left alone once started
* **Remote Interface:** Wireless hotspot (“BirdProject”) allows remote control and monitoring
* **Weatherproofing:** Sealed enclosure with outdoor deck paint, caulk, and slanted roof
* **Thermal Stability:** Maintains ~55°C during 14+ hour continuous operation


## Project Structure

* software  - Python web controller, physical controls code, systemd configs, video playback (mpv + Cage)
  [Software](Code/)
* media     - Processed bird footage, recorded videos
  [Media](media/)
* docs      - Reports, assembly guides, and research documentation
  [Documentation](Documentation/)



## Features

* **4-Way Holographic Projection**
  Prism enables 360° visibility

* **Predatory Behavioral Loop**
  High-frame-rate (up to 120fps) optimized for bird vision

* **"BirdProject" Control Panel**
  Mobile-friendly web UI for system control

* **External Integration**
  Broadcasts system status ("PLAYING" / "IDLE") via URL

* **Rugged Construction**
  Built to withstand wind, rain, and animal interference


## System Architecture

* **Compute Module:** Raspberry Pi 5 running a custom Wayland session
* **Display:** Internal 27 by 14-inch monitor
* **Optics:** 4-piece plexiglass trapezoidal prism (base = monitor width / 6)
* **Software Stack:** Python + Flask, subprocess control, systemd services
* **Power:** Spliced 120V extension cord with sealed entry point


## Bill of Materials (BOM)
[Documentation](Documentation/)
### Tools Used

* **Software:** Kdenlive, SAM 2, Python/Flask, systemd
* **Hardware:**

  * Table saw
  * Hand saw
  * Soldering iron (for power cable)
  * Hot glue gun
  * 3D printer (Raspberry Pi case)


## Assembly Overview

### 1. Lens Fabrication

* Cut 4 trapezoidal plexiglass pieces

  * Top: 15"
  * Bottom: 2.5"
  * Height: 8.75"
* Sand edges and glue into prism shape

### 2. Case Construction

* Build wooden enclosure sized for 27" by 14" monitor
* Apply outdoor deck paint for protection

### 3. Electronics Integration

* Install Raspberry Pi 5 and monitor
* Route power cord through sealed hole

### 4. Software Setup

* Flash Raspberry Pi OS
* Install `bird-system.service`
* Deploy `remote.py` controller

### 5. Final Sealing

* Caulk all seams
* Secure slanted roof


## Operating Instructions

### Power On

Plug in the unit — system boots and begins playback within ~25 seconds.

### Connect

* **SSID:** BirdProject
* **Password:** hol0b1rd143

### Control Panel

Navigate to:

```
http://10.42.0.1:5000
```

* Switch videos
* Monitor system status
* Control playback


## Acknowledgements

Developed by:

* Ryan Leggett
* Caleb Miller
* Nathan Sugars
* Andrew Kroll
* Tyler Goeman

Supported by the Open Source Hardware Enterprise (OSHE) at Michigan Technological University.


## Helpful Links

https://kdenlive.org
https://projects.raspberrypi.org/en/projects/getting-started-with-guis
https://doi.org/10.1242/jeb.209031


