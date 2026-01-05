# A 4×3 Keyboard for ZMK firmware configuring tryout

[Traditional Chinese version](./README_zhTW.md)

Before start building the final Dvorak-optimized ortholinear southpole keyboard, I'm going to build a smaller prototype that has the same function as the final keyboard to seeing the feasibility and being the springboard of the final product.

Built 50 times and finally have the first success building

### The development of this project is still in progress

`.uf2` is at `Action` tab, click the first one, in `Artifacts` section, there's a `firmware` object. Click to download the `.zip`, unzip it and you'll have the `.uf2`.\
<!-- TODO Write burning instruction hère -->

<!-- 
Turn Seeed XIAO into bootloader mode by double clicking the "RST" button on the board
**after** the board is connected to PC
 -->

## Functions

- 4x3 matrix activated
- USB Wired connect
- Simple typing
- ZMK Studio support

### Functions to be add
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

---

# History

Latest first

## ZMK Studio function added successfully
On **117th build**(2026 Jan. 5→6 Midnight) FUNCTION COMPLETED  
Turns out the real problem is I shouldn't make MISO (D9) a `CS` (AKA `latch`) pin while using SPI.  
**REMEMBER EVERYONE!** or you'll waste a whole lot of time.

On **107th build**(2026 Jan. 5) I finally make 74595-added version passed building.  
Need to be configure more to make it able to function normally, but it passed and basically runnable.  
Everything's finally going to reach a stage of an end…

On **85th build**(2025 Dec. 26) I finally added ZMK Studio successfully  
Okay, so every problem is from the `chosen` node in the [.dtsi](./boards/shields/zmk_4x3test/zmk_4x3test-layouts.dtsi) file. It's really "the chosen node"

## Clarified Column and Row
On **66th build**(2025 Nov. 11) I finally found that I misunderstand the meaning of column and row.  
As a little note, I'm going to make a note here

＼|Column 0|Column 1|Column 2
--|--------|--------|--------
Row 0|RC(0,0)|RC(0,1)|RC(0,2)
Row 1|RC(1,0)|RC(1,1)|RC(1,2)

## First successful build

Finally built successfully built on **51th build**, and realized it on **54th build**.  
The reason I'm not realized right when succeeded is that I was using my Samsung Galaxy Tab S7 FE + [VS code web version](https://vscode.dev), and it was laggy, so it's hard to see the progress with a very real-time experience.
