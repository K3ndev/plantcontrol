# PlantControl
Make your plantpot care about the plant

<img width="1182" height="854" alt="image" src="https://github.com/user-attachments/assets/43174cda-7d5d-4d06-a59e-f9dee39e8c2f" />


## Features

* Compatible with all plantpots
* Dont have to water your plants
* Numbers about humidity and soil mositior
* Numbers about ewerithing
* Will warn you if its water is geting low

## How to Build It
1. **Gathering the parts:** Order the PCBs. Print the printable things. Order the parts from the bom. (If you want to add leds you will need an aluminum sheet like mine in the files)
2. **Assembly**: Solder in ewerything what is need to.
3. **Programing:** Put the esp32 in boot mode. Flash the frimware pull out from boot mode. (follow this [MicroPython Flashing Guide](https://georgefreedom.com/ignition-sequence-how-to-flash-micropython-onto-your-esp32/)
4. **Wireing:** Conect all the things on to its place.
5. **Final touches:** place the device in to the 3dprinted cover and put the sensors to they place and power it on.
6. **Done!** Your plant controller is ready to go.

> **Pro Tip:** On first boot (or if it cannot connect to a saved network), the device will host a Wi-Fi Access Point. Connect to it to enter your local Wi-Fi SSID and password via the captive portal. Don't forget to enter your ThingSpeak API key in the configuration file to enable telemetry logging!

## How It Works

PlantControl is an IOT dievice for monitoring almost ewerything around your pant. It also can water it and giw it light. Its powered by an esp32-C6. The frimware is using threading so ewerything gets can do its own thing.

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=https://github.com/csuszcukk/plantcontrol/tree/main/pcb/mainboard)

### Core Architecture

* **Sensor Data Acquisition:** The system mesures soil moisture,  light, and air temperature/humidity. 
* **Automated Logic & Safety:** If soil moisture drops below the predefined threshold, the MCU triggers a relay to activate the water pump.
* **Local UI & Status:** A circular GC9A01 SPI display provides real-time readout of plant metrics and device status directly on the enclosure.
* **Power & Load Management:** High-side MOSFET switching ensures power is delivered efficiently with pwm so the LED can dimm in litel light.
* **Connectivity & Telemetry:** Integrated Wi-Fi connects to local infrastructure to stream to ThingSpeak. If network connection fails, it automatically spins up a Wi-Fi Access Point for re-configuration.

## Component Sourcing & Logistics

I used two vendors:

- **LCSC:** Used for standard SMD components, and for the ESP32 to take advantage of low pricing.
- **HESTORE:** Used for sensors, modules, and components unavailable on LCSC.

All BOM prices from HESTORE have been converted from HUF to USD using current market exchange rates.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
