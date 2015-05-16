# Control a Relay Switch over Bluetooth

This sketch uses the RedBearLab BLE shield (<http://redbearlab.com/bleshield/>)
to expose a service for controlling a light.

## Setup

Copy the `BLE/` directory to your Arduino library

## GATT Profile

The sketch exposes a Service, called `Light`, with UUID
`FD94-0001-5A8A-6451-FFA3-A512-84B6515F`. The service exposes three
Characteristics:

  1. _On off_ (`FD94-0000-5A8A-6451-FFA3-A512-84B6515F`) can be written to.
     Writing the value `1` means turn on, writing the value `0` means turn off.

  2. _RGB Color_ (`FD94-0002-5A8A-6451-FFA3-A512-84B6515F`) can be written to.
     Accepts an CSS-style RGB color (e.g. two bytes each for red, green and
     blue). Currently unused by the sketch.

  3. _Light Level_ (`FD94-0011-5A8A-6451-FFA3-A512-84B6515F`) can be written to.
     Takes a one byte intensity level. Currently unused by the sketch.

## Wiring

Stack the BLE shield on an Arduino Uno and connect an LED or relay switch to
port 2.

