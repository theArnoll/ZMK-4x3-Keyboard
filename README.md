# A 4×3 Keyboard for ZMK firmware configuring tryout

[Traditional Chinese version](./README_zhTW.md)

Before start building the final Dvorak-optimized ortholinear southpole keyboard, I'm going to build a smaller prototype that has the same function as the final keyboard to seeing the feasibility and being the springboard of the final product.

Built 50 times and finally have the first success building

### The development of this project is still in progress

`.uf2` is at `Action` tab, click the first one, in `Artifacts` section, there's a `firmware` object. Click to download the `.zip`, unzip it and you'll have the `.uf2`.\
<!-- TODO Write burning instruction hère -->

## Functions

- 3x3 matrix activated now
- USB Wired connect
- Simple typing

So it's like a minimum viability test in this stage.

### Functions to be add

- Full 3x4 matrix activate
- ZMK Studio support\
   (The support should've been included in current configuration, but [&studio_unlock](&studio_unlock) haven't officially included to keymap yet, so not tested)
- Bluetooth connection (Using USB Power)

## Hardware requirement

### Everything you need for this project

- Seeed XIAO nRF52840
- 16 mechanical keyboard switches
- My 4×3 matrix DIP PCB\
  You can buy it from a shopping platform in Taiwan called Shopee in the future, and the PCB manufacturing file will upload in the future.

### Things you will need in future updates

- 74HC595 IC
- (Optional) LED bar graph display
- (Optional) 4 Resistors for ↑

---

Everything here are basically all referenced to the official document. You can check out [references.md](./references.md) for more detailed information.\
The order of references in the file should be in chronological order of use.
