# Corne Keyboard ZMK Config

This repository contains the ZMK configuration for a Corne keyboard with nRF52840 Pro Micro controllers.

## Features

- ZMK Studio support for live keymap editing
- RGB underglow support
- OLED display support
- Bluetooth connectivity
- Deep sleep mode
- GitHub Actions for automatic firmware builds

## Flashing Instructions

1. Put your keyboard into bootloader mode
2. Download the latest firmware from GitHub Actions artifacts
3. Copy the `.uf2` files to the keyboard's mass storage device

## Layout

The default layout includes:
- QWERTY base layer
- Lower layer with numbers and Bluetooth controls
- Raise layer with symbols
- Adjust layer with RGB controls

## Building Locally

```bash
docker run --rm -v $(pwd):/app -w /app zmkfirmware/zmk-build-arm:stable \
  west build -s zmk/app -b nice_nano_v2 -- -DSHIELD=corne_left -DZMK_CONFIG=/app/config
```

## ZMK Studio

This configuration includes ZMK Studio support. Connect your keyboard and use the ZMK Studio app to modify your keymap in real-time.