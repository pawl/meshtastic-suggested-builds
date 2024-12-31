# Meshtastic Suggested Builds
This is an unofficial compilation of personal and community-sourced Meshtastic builds.

## Build 1: Heltec T114 with GPS and Display

### Parts List
- **Heltec Mesh Node T114 with Display**: Previously available at [muzi.works](https://muzi.works/products/heltec-mesh-node-t114), but now best sourced directly from [Heltec](https://heltec.org/project/mesh-node-t114/).
- **GPS Module** (optional): [Heltec GPS Module for Mesh Node T114](https://muzi.works/products/heltec-gps-module-for-mesh-node-t114).
- **Battery**: [1200mAh battery from musi.works](https://muzi.works/products/h1-battery)
- **Case**: [H2T Case for Heltec T114 with GPS](https://www.printables.com/model/982046-h2t-case-for-heltec-t114-with-gps-running-meshtastic), allows for a wider range of antennas with wider bases compared to the previous H1 version for the Heltec V3.
- **Antenna**: Highly recommended Linx ANT-916-CW-HW-SMA for portable nodes [Available here](https://www.mouser.com/ProductDetail/712-ANT-916-CW-HWSMA).

### Pros
- Improved battery life compared to the older v3 model and fixes heat issues while charging with the battery plugged in.
- Additional button improves navigation between info pages without needing to connect to a phone.
- Adds another power input for solar which the v3 didn't have. (haven't tested this yet)

## Build 2: Solar Node Setup

Based on: [austinmesh.org's Building a Solar-Powered Repeater for Meshtastic](https://www.austinmesh.org/devices/#solar)

### Parts List
- **RAKwireless WisBlock Meshtastic Starter Kit US915**: [RAK Wireless Kit](https://store.rokland.com/products/rak-wireless-wisblock-meshtastic-starter-kit) (SKU 116016).
- **Antenna**: 5.8 dBi N-Male Omni Outdoor Helium 915 MHz Antenna [Available here](https://store.rokland.com/products/5-8-dbi-n-male-omni-outdoor-915-mhz-antenna-large-profile-32-height-for-helium-rak-miner-2-nebra-indoor-bobcat).
- **Solar Panel**: Soshine Mini Solar Panel - USB Solar Panel Charger 5v 6w [Available on Amazon](https://www.amazon.com/Soshine-Mini-Solar-Panel-Monocrystalline/dp/B099RSLNZ4).
  - **Mounting Bracket**: 3D printed bracket for Soshine 6W solar panel [Available on Printables](https://www.printables.com/model/223030-bracket-mount-for-soshine-6w-5v-usb-solar-panel).
- **Enclosure**: Junction Box, ABS Plastic, IP65 Waterproof Dustproof Universal Electrical Enclosure [Available on Amazon](https://www.amazon.com/LMioEtool-Dustproof-Waterproof-Electrical-150mmx100mmx70m/dp/B07KXRW62F).
  - **Vent**: For moisture release [Available on Amazon](https://www.amazon.com/Dusproof-Waterproof-Lighting-Breather-Pressure/dp/B0BKY2LLLV).
  - **Drill Bit**: For drilling holes in the enclosure [Available on Amazon](https://www.amazon.com/SALI-Tungsten-Carbide-Titanium-Plated-Stainless/dp/B0CG94QCJM).
  - **Sealing Tape**: For antenna and solar panel connections [Available on Amazon](https://www.amazon.com/Proxicast-Pro-Grade-Weatherproof-Self-Fusing-Electrical/dp/B00K5GW67O).
- **Battery**: Voltaic Systems V25 USB Battery Backup [Available on Amazon](https://www.amazon.com/Voltaic-Systems-Formerly-Battery-Samsung/dp/B07ZS3WYZY).
- **Micro USB Extension**: For connecting the solar panel to the enclosure [Available on Amazon](https://www.amazon.com/Kework-Extension-Motorcycle-Dashboard-Transferring/dp/B082HZKVP1).
- **WisBlock Mount**: For securing the RAK board inside the enclosure [Available on Printables](https://www.printables.com/model/891096-rak19007-wisblock-base-board-mount).

### Pros
- Self-sustaining with solar power for long-term deployment.
- High elevation potential for clear line of sight.

### Cons
- Not reliable as-is, experiencing voltage drops and system brownouts.
  - Currently exploring using a larger solar panel or swapping the battery with protected 18650 cells and the [Waveshare Solar Power Manager Module (D)](https://www.waveshare.com/solar-power-manager-d.htm) to hopefully mitigate voltage issues.

## Build 3: Non-Portable Heltec V3

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: [Heltec Kit](https://muzi.works/products/heltec-kit).
- **Antenna**: 3 dBi N-Male RAK Wireless Fiberglass Outdoor Antenna [Available here](https://store.rokland.com/products/3-dbi-rak-brand-fiberglass-outdoor-antenna-bracket-mount-for-rak-bobcat-sensecap).
- **Case**: RAK19007RAK5005 case for Meshtastic N-type antenna, only used n-type-rak-frame.stl file for the frame [Available on Printables](https://www.printables.com/model/997695-rak19007rak5005-case-for-meshtastic-n-type-antenna).
- **Coaxial Pigtail Jumper Cable**: Proxicast 8 inch U.FL to N Female cable [Available on Amazon](https://www.amazon.com/Proxicast-Low-Loss-Coaxial-Pigtail-Bluetooth/dp/B09GJJSXX8).

### Pros
- Reliable and sturdy for fixed locations.
- Uses powerful, outdoor-rated antenna for greater signal coverage.

### Cons
- Requires permanent installation location.

## Reference Links
- [Meshtastic Antenna Testing GitHub](https://github.com/meshtastic/antenna-reports?tab=readme-ov-file) for antenna performance analysis.
- [Meshtastic Official Antenna Recommendations](https://meshtastic.org/docs/hardware/antennas/) for guidance on selecting the best antennas for your builds.

# Archived Builds

## Portable Heltec V3 Setup

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: [Heltec Kit](https://muzi.works/products/heltec-kit) includes the board, U.FL to SMA pigtail cable, stubby antenna (not recommended for use).
- **Antenna**: Recommended [17cm GIZONT](https://www.aliexpress.us/item/3256804421300249.html) or [20cm GIZONT](https://www.aliexpress.us/item/3256806172931647.html) from AliExpress for improved range.
- **Battery**: Refer to Build 1 for battery details.
- **Case**: The most popular 3D printable Meshtastic case, [H1 Case for Heltec V3](https://www.printables.com/model/741974-h1-case-for-heltec-v3-running-meshtastic), created by musi.works and also available for purchase at [muzi.works](https://muzi.works/products/h1-case-for-heltec-v3-running-meshtastic).

### Setup Notes
- **Flashing the Device**: The Heltec V3 needs to be flashed for Meshtastic compatibility. Use the Meshtastic flasher tool available at [Meshtastic Flasher](https://flasher.meshtastic.org/).

### Pros
- Compact design that's very portable.
- Very popular radio board with lots of community support.

### Cons
- Significant heat generation near the charging port while charging with the battery connected. [More details](https://www.reddit.com/r/meshtastic/comments/1daiee2/heltec_v3_overheats_with_battery_attached/)

## Portable Heltec V3 with Linx Antenna

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: As above.
- **Antenna**: Highly recommended Linx ANT-916-CW-HW-SMA for portable nodes [Available here](https://www.mouser.com/ProductDetail/712-ANT-916-CW-HWSMA).
- **Case**: [Alley Chat HT Pocket Case](https://www.printables.com/model/920722-alley-chat-ht-pocket-heltec-lora-32-v3-case-by-all), available for purchase at multiple locations: [Goods by Pratik](https://goodsbypratik.etsy.com/listing/1733566732), [Etsy Listing](https://www.etsy.com/listing/1765871840), [3G3D Printing](https://3g3dprinting.etsy.com/listing/1704048054), [Travis Edson](https://travisedson.com/shop/product/alleychat-ht-pocket-case/), or for UK customers, [3D Chicken](https://3dchicken.co.uk/products/heltec-v3-ht-pocket-the-worlds-smallest-heltec-v3-case).
- **Battery Stability**: A cardboard shim may be needed inside the case to secure the 1200mAh battery from moving around. Refer to Build 1 for battery details.

### Pros
- Supports a wider range of antennas.

### Cons
- Less compact due to the antenna protruding from the top.
- Retains the power efficiency and heat issues observed in previous builds.
