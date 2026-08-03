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
- Adds another power input for solar which the v3 didn't have. (haven't tested this yet)

### Planned Upgrades

Main goal is the charging problem: more runtime so it needs charging less often.

- Battery upgrade (ordered): swapping the 1200mAh h1-battery for the [muzi.works H2T battery](https://muzi.works/products/h2t-battery), 2000mAh (8 x 31 x 61.5mm). Same 1.25mm connector and it fits the existing H2T case, so it's a straight swap with no rework, about two-thirds more capacity.
- GPS is a bigger lever than capacity. The GPS module is the dominant drain (the T114 runs 100+ hours with GPS off versus dozens of hours with it on). Plan to set GPS to a fixed position or an occasional fix instead of continuous, and add a screen timeout. Combined with the 2000mAh cell that should move runtime from a day or two up to multiple days.
- Considered, not doing yet: reprinting a case with a physical power switch (Andrey Lifar 103450 design, or zerofox3D Nibbler2) so it can be fully off in storage instead of powering down through the app. Needs a narrower 103450 cell and a reprint, so only worth it if standby drain gets annoying. Note the spare 1800mAh 604050 cell does not fit any of these cases (too wide at 40mm); it's earmarked as the solar node's buffer cell instead.
- Optional QoL: a magnetic USB-C charging adapter, since the real issue is forgetting to plug in and this lowers the effort.

Antenna stays. The Linx ANT-916 is already a strong portable antenna.

## Build 2: Solar Node Setup

Based on: [austinmesh.org's Building a Solar-Powered Repeater for Meshtastic](https://www.austinmesh.org/devices/#solar)

### Parts List
- **RAKwireless WisBlock Meshtastic Starter Kit US915**: [RAK Wireless Kit](https://store.rokland.com/products/rak-wireless-wisblock-meshtastic-starter-kit) (SKU 116016).
- **Antenna**: 5.8 dBi N-Male Omni Outdoor Helium 915 MHz Antenna [Available here](https://store.rokland.com/products/5-8-dbi-n-male-omni-outdoor-915-mhz-antenna-large-profile-32-height-for-helium-rak-miner-2-nebra-indoor-bobcat).
- **Solar Panel**: Soshine Mini Solar Panel - USB Solar Panel Charger 5v 6w [Available on Amazon](https://www.amazon.com/Soshine-Mini-Solar-Panel-Monocrystalline/dp/B099RSLNZ4).
  - Chosen for faster shipping and because more 3D printed mounts exist for this size.
  - **Mounting Bracket**: 3D printed bracket for Soshine 6W solar panel [Available on Printables](https://www.printables.com/model/223030-bracket-mount-for-soshine-6w-5v-usb-solar-panel).
    - Requires M4 nuts and bolts to attach the panel.
  - **USB-A to USB-C Cable**: Cable Matters USB-C Adapter [Available on Amazon](https://www.amazon.com/Cable-Matters-Adapter-USB-C-Inches/dp/B00UUBQ0U8) for connecting the solar panel to the enclosure.
- **Enclosure**: Junction Box, ABS Plastic, IP65 Waterproof Dustproof Universal Electrical Enclosure [Available on Amazon](https://www.amazon.com/LMioEtool-Dustproof-Waterproof-Electrical-150mmx100mmx70m/dp/B07KXRW62F).
  - Clamps provide a tighter seal compared to screw-based enclosures, and are easier to re-open.
  - **Vent**: For moisture release [Available on Amazon](https://www.amazon.com/Dusproof-Waterproof-Lighting-Breather-Pressure/dp/B0BKY2LLLV).
  - **Drill Bit**: For drilling holes in the enclosure [Available on Amazon](https://www.amazon.com/SALI-Tungsten-Carbide-Titanium-Plated-Stainless/dp/B0CG94QCJM).
  - **Sealing Tape**: For sealing around the antenna connection and where the solar panel connects to the exterior [Available on Amazon](https://www.amazon.com/Proxicast-Pro-Grade-Weatherproof-Self-Fusing-Electrical/dp/B00K5GW67O).
- **Power Management**: Waveshare Solar Power Manager Module (D) [Available here](https://www.waveshare.com/solar-power-manager-d.htm).
  - Supports 6V~24V Solar Panel and Type-C Power Adapter, 5V/3A Regulated Output.
  - **Battery**: 18650 LG MJ1 INR18650-MJ1 3500mAh High Discharge Protected Button Top batteries [Available here](https://illumn.com/18650-lg-mj1-inr18650-mj1-high-discharge-protected-button-top.html).
  - **Connection**: Use the Waveshare 5V output pins connected to the RAK Solar-In port (not USB-C) for proper voltage regulation and brownout protection.
  - **Note**: Previously used Voltaic Systems V25 USB Battery Backup, but it caused voltage instability and brownouts requiring device reconfiguration. The Waveshare module has been stable for 9+ months.
  - **Important**: Do NOT use the USB-C port for charging the device directly, as this can cause voltage instability and device resets requiring reconfiguration in the app.
  - **Reference**: [Detailed explanation of proper power connection](https://www.reddit.com/r/meshtastic/comments/1fv5zli/comment/lq6a05s/) for brownout protection and battery management.
- **Solar Panel Connection**: Cut off the USB connector from the solar panel cable and strip the positive and negative wires to connect directly to the Waveshare module's dedicated SOLAR IN terminal blocks (6V~24V input).
- **USB Flush Mount Cable**: Kework USB Type C Mount, 0.3 Meter USB-C Male to Female Flush Mount Panel Mount Extension AUX Cable [Available on Amazon](https://www.amazon.com/Kework-Extension-Motorcycle-Dashboard-Transferring/dp/B082HZKVP1).
  - Provides waterproof connection point on enclosure bottom. Any USB connector type works since the end gets cut off for direct wiring to solar terminal blocks.
- **WisBlock Mount**: For securing the RAK board inside the enclosure [Available on Printables](https://www.printables.com/model/891096-rak19007-wisblock-base-board-mount).
- **Waveshare Module Mount**: 3D printed adapters to mount the Waveshare Solar Power Manager above the WisBlock to save space [Available on Printables](https://www.printables.com/model/890829-meshtastic-rak-waveshare-solar-enclosure-adapters).

### Pros
- Doesn't require being plugged into a power outlet, so you can potentially put it on a roof for better line of sight.

### Cons
- Currently investigating limited range issues (the 1W booster upgrade below is the main fix for this).

### Planned Upgrades

Moving this node to the RAK 1W booster to fix the range issue, and rebuilding into a bigger enclosure because the current one is too cramped for the larger board plus a buffer battery. Parts, status, and reasoning below.

Radio and power:
- WisMesh 1W Booster Kit (RAK10724), 915 MHz (have it): [link](https://store.rakwireless.com/products/meshtastic-1w-lora-booster-kit-rak3401). Much higher TX power plus better receive sensitivity from the built-in SAW filter and LNA, which is the main range fix. Built on the same RAK19007 base board, so the base-board mount and antenna carry over. Ordered from RAK directly since Rokland has been out of stock for months. The populated board (core module plus the separate 1W module in the next slot) is physically longer than the old RAK4631, which is part of why the old box no longer fits.
- Buffer LiPo (have it): MakerFocus 3000mAh flat cell with a JST PH 2.0 plug already wired for RAK polarity. The 1W radio can't run off the base board's 3.3V rail and needs a battery on the board to absorb the transmit surge. Just having this connected is what unlocks full 1W. Chose 3000mAh on purpose: the base board charges a connected cell slowly, so a smaller buffer stays reliably topped, while the 18650s on the Waveshare stay the main storage. (This replaces the earlier plan to reuse the 1800mAh muzi 604050 cell; that cell is freed up and is too wide for the T114 cases anyway. The MakerFocus is worth $13 to skip the connector re-termination and polarity work.)
- Power wiring change: feed the Waveshare 5V output into the booster's EX_5V input, not the base-board Solar-In as before, with the module power jumper set to EX_5V. EX_5V powers the whole stack and keeps the buffer charged. The 5V lead for this comes in the kit. Keep the 18650s on the Waveshare as the reservoir. Still do NOT charge through the base-board USB-C port.
- Solar panel upgrade (have it): [Voltaic 9W 18V ETFE (P108)](https://voltaicsystems.com/9-watt-18v-panel-etfe/), with the [BK103 Large bracket](https://voltaicsystems.com/BK103/) and [ETFE screw set](https://voltaicsystems.com/mount-set-etfe/). The 1W board draws more than the RAK4631, so the 6W panel is undersized. Chose the 18V version over the 10W 6V one because the Waveshare needs a 6 to 24V input, and a 6V panel (peak around 5.7V) drops below that floor when hot. Wire it into the Waveshare SOLAR IN using the [Voltaic extension-with-leads](https://voltaicsystems.com/extension-with-exposed-leads) so the panel's own cable stays intact; watch polarity (confirm with a meter, do not trust wire color).

Enclosure and mounting:
- New enclosure (to buy): LMioEtool 220x170x110mm (8.7 x 6.7 x 4.3 inch), grey opaque cover, with the removable mounting plate. This is the larger size of the same LMioEtool line as the current box. The old 150x100x70 was a tight fit even for the RAK4631, and won't hold the longer 1W board plus the buffer cell with room to secure anything. Grey opaque, not clear: a clear lid on a Dallas roof is a greenhouse. The removable plate is the other reason to switch, since everything mounts on the bench and drops in, so drilling happens in an empty shell.
- Cable entry: retire the USB-C flush-mount pass-through. The panel now wires straight into the Waveshare, so replace it with a PG9 cable gland (from a PG7/PG9/PG11 assortment). The Voltaic lead is thinner than the gland's minimum clamp, so build it up with a few turns of self-fusing tape before tightening. Mount the gland on the bottom face pointing down so water sheds off it. Two holes total in the new box: the N antenna bulkhead up top, and this gland on the bottom.
- Internal mounting: screw-down saddle cable-tie mounts (to buy, black nylon, screw type not adhesive) fixed to the new plate, instead of relying on the grid. Adhesive-backed mounts let go in rooftop heat, so avoid those. Tie the 18650 holder and the buffer cell to the shaded lower area, not against the 1W module.

Panel placement and heat (Dallas):
- The panel can't sit directly over the box because the antenna exits the top of the enclosure. Mount the panel offset and slightly above the box, tilted about 35 degrees facing south. At summer noon the sun is nearly overhead, so a tilted panel drops its shadow almost straight down onto the box, which is the shade you want when heat is worst. The antenna runs straight up a few inches to the side of the panel edge so it stays clear of the panel's near field. With a roughly 3ft antenna, almost all of the radiating length is above the panel anyway, so shading the box is the priority over any tiny near-field concern.
- Add a silica gel desiccant pack inside (Texas humidity), keep a moisture breather/vent, and consider running TX around 27 dBm instead of the full 30 to cut heat and power draw. The receive-sensitivity gain from the filtered front end holds regardless of TX level.

Config:
- Flash the firmware-rak3401-1watt build via [flasher.meshtastic.org](https://flasher.meshtastic.org/), erase/factory first, region US / 915 MHz. Set the power jumper to EX_5V. Role stays CLIENT (already is), not ROUTER, since a rooftop isn't a dominant enough site and a misplaced router consumes hops early. Never power the board on without the antenna connected, it can damage the RF stage at 1W.

Build order: assemble and flash/config the board on the bench, drill the empty shell, then drop the loaded plate in and land the antenna and solar connections last.

Optional, only if range is still short after the swap: a [915 MHz cavity filter](https://acasom.com/products/915mhz-cavity-filter-for-helium-network-amplifier-filter-sma-type-high-out-band-rejection), in case nearby transmitters are desensitizing the receiver. The booster's built-in SAW filter already helps, so hold off until the swap is tested.

Carries over from the current build: Waveshare Solar Power Manager D, the 18650 LG MJ1 cells, the 5.8 dBi N-male antenna, and the spare U.FL to N pigtail (the RAK13302 uses an IPEX connector, so it fits).

## Build 3: Non-Portable Heltec V3

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: [Heltec Kit](https://muzi.works/products/heltec-kit).
- **Antenna**: 3 dBi N-Male RAK Wireless Fiberglass Outdoor Antenna [Available here](https://store.rokland.com/products/3-dbi-rak-brand-fiberglass-outdoor-antenna-bracket-mount-for-rak-bobcat-sensecap).
- **Case**: for Meshtastic N-type antenna, only used n-type-rak-frame.stl file for the frame [Available on Printables](https://www.printables.com/model/997695-rak19007rak5005-case-for-meshtastic-n-type-antenna).
- **Coaxial Pigtail Jumper Cable**: Proxicast 8 inch U.FL to N Female cable [Available on Amazon](https://www.amazon.com/Proxicast-Low-Loss-Coaxial-Pigtail-Bluetooth/dp/B09GJJSXX8).

### Pros
- Reliable and sturdy for fixed locations.
- Uses powerful, outdoor-rated antenna for greater signal coverage.

### Cons
- Requires being indoors (preferrably near a window) and plugged into power.

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
