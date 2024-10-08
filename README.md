# Meshtastic Suggested Builds
This is an unofficial compilation of personal and community-sourced Meshtastic builds.

## Build 1: Portable Heltec V3 Setup

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: [Heltec Kit](https://muzi.works/products/heltec-kit) includes the board, U.FL to SMA pigtail cable, stubby antenna (not recommended for use), and a 1200mAh battery.
- **Antenna**: Recommended [17cm GIZONT](https://www.aliexpress.us/item/3256804421300249.html) or [20cm GIZONT](https://www.aliexpress.us/item/3256806172931647.html) from AliExpress for improved range.
- **Case**: The most popular 3D printable Meshtastic case, [H1 Case for Heltec V3](https://www.printables.com/model/741974-h1-case-for-heltec-v3-running-meshtastic), created by musi.works and also available for purchase at [muzi.works](https://muzi.works/products/h1-case-for-heltec-v3-running-meshtastic).

### Setup Notes
- **Flashing the Device**: The Heltec V3 needs to be flashed for Meshtastic compatibility. Use the Meshtastic flasher tool available at [Meshtastic Flasher](https://flasher.meshtastic.org/).

### Pros
- Compact design that's very portable.
- Very popular radio board with lots of community support.

### Cons
- Significant heat generation near the charging port while charging with the battery connected. [More details](https://www.reddit.com/r/meshtastic/comments/1daiee2/heltec_v3_overheats_with_battery_attached/)

## Build 2: Heltec V3 with Linx Antenna

### Parts List
- **Heltec WiFi LoRa 32 V3 Board**: As above.
- **Antenna**: Highly recommended Linx ANT-916-CW-HW-SMA for portable nodes [Available here](https://www.mouser.com/ProductDetail/712-ANT-916-CW-HWSMA).
- **Case**: [Alley Chat HT Pocket Case](https://www.printables.com/model/920722-alley-chat-ht-pocket-heltec-lora-32-v3-case-by-all), available for purchase at multiple locations: [Goods by Pratik](https://goodsbypratik.etsy.com/listing/1733566732), [Etsy Listing](https://www.etsy.com/listing/1765871840), [3G3D Printing](https://3g3dprinting.etsy.com/listing/1704048054), [Travis Edson](https://travisedson.com/shop/product/alleychat-ht-pocket-case/), or for UK customers, [3D Chicken](https://3dchicken.co.uk/products/heltec-v3-ht-pocket-the-worlds-smallest-heltec-v3-case).
- **Battery Stability**: A cardboard shim may be needed inside the case to secure the 1200mAh battery from moving around.

### Pros
- Supports a wider range of antennas.

### Cons
- Less compact due to the antenna protruding from the top.
- Retains the power efficiency and heat issues observed in Build 1.

## Solar Node Setup

TODO: Enclosure and weatherproofing still under development. (Might use [austinmesh.org's suggestions](https://www.austinmesh.org/devices/#parts-list).)

### Parts List
- **RAKwireless WisBlock Meshtastic Starter Kit US915**: [RAK Wireless Kit](https://store.rokland.com/products/rak-wireless-wisblock-meshtastic-starter-kit) (SKU 116016).
- **Antenna**: ALFA AOA-915-5ACM Omni Outdoor 915MHz Antenna [Available here](https://store.rokland.com/products/alfa-aoa-915-5acm-5-dbi-omni-outdoor-915mhz-802-11ah-mini-antenna-for-lora-halow-application).
- **Solar Connector Cables**: RAK Wireless Solar Connector Cables [Available here](https://store.rokland.com/products/rak-wireless-solar-connector-cables-solar-wires-5pcs-pid-910116).
- **Bulkhead Pigtail Cable Extension**: UFL(IPEX/IPX) Mini PCI to N-Female Bulkhead Pigtail Cable Extension [Available here](https://store.rokland.com/products/uflipex-ipx-mini-pci-to-n-female-bulkhead-pigtail-cable-extension-rg178).

### Pros
- Optimized for long-term outdoor deployment.
- High elevation potential for clear line of sight.

### Cons
- TODO

## Reference Links
- [Meshtastic Antenna Testing GitHub](https://github.com/meshtastic/antenna-reports?tab=readme-ov-file) for antenna performance analysis.
- [Meshtastic Official Antenna Recommendations](https://meshtastic.org/docs/hardware/antennas/) for guidance on selecting the best antennas for your builds.
