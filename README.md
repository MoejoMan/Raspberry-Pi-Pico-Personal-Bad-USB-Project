# Raspberry Pi Pico USB HID Project

An educational hardware security project. A Raspberry Pi Pico is set up to present itself to a computer as a USB keyboard, which is the mechanism behind "Rubber Ducky" style keystroke injection attacks. The aim is to understand how these attacks work so they can be detected and blocked.

## Approach

- **Hardware:** Raspberry Pi Pico running CircuitPython.
- **Firmware:** built on the open source [pico-ducky](https://github.com/dbisu/pico-ducky) project.
- **Environment:** tested only on machines and virtual machines that I own.

## Scope and rules

- Use only on devices you own or have written permission to test.
- No payloads are published in this repository, on purpose.
- Nothing here collects credentials or personal data.

## What this project taught me about defence

| Layer | Control |
|---|---|
| Prevent | Device control policy that only allows approved USB devices (Group Policy on Windows, USBGuard on Linux) |
| Prevent | Lock the screen when away, and control physical access to USB ports |
| Detect | Windows event 6416, "a new external device was recognised", with Plug and Play auditing enabled |
| Detect | Process creation logging (event 4688 with command lines) and PowerShell script block logging (event 4104) |
| Detect | Endpoint tools that flag keyboards typing faster than a human can |

## Status

Setup notes only. Lab write ups will be added here as they are completed.