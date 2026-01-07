# A 4×3 Keyboard for ZMK firmware configuring tryout

[Traditional Chinese version](./README_zhTW.md)

Before start building the final Dvorak-optimized ortholinear southpole keyboard, I'm going to build a smaller prototype that has the same function as the final keyboard to seeing the feasibility and being the springboard of the final product.

Built 50 times and finally have the first success building

## The bluetooth wireless function is still under development

## How to burn the firmware into your Seeed XIAO

First, you need the `.uf2` file of this project. The `.uf2` file is in `Action` tab. Go to the tab and click the first one in the list. In `Artifacts` section, there's a `firmware` object. Click the download icon on the right to download the `.zip`, unzip it and you'll have the `.uf2`.

After that, turn Seeed XIAO into bootloader mode by double tapping the `RST` button on the board **after** the board is connected to PC. Your Seeed XIAO will appear in File Explorer like an USB called `XIAO-SENSE`. If it doesn't come with that name, at least you'll able to recognize the device.

Drag the `.uf2` file into the "USB". After the file transfer is done, Seeed XIAO will automatically eject itself and reboot into the code. If it functions correct, you're done burn the firmware into your Seeed XIAO.

## Functions

- 4x3 matrix activated
- USB Wired connect
- Simple typing
- ZMK Studio support

### Functions to be add
- Bluetooth connection (With BL-5C battery)

## Hardware requirement

### Everything you need for this project

- Seeed XIAO nRF52840
- 16 mechanical keyboard switches
- My 4×3 matrix DIP PCB\
  You can buy it from a shopping platform in Taiwan called Shopee in the future, and the PCB manufacturing file will upload in the future.
- 74HC595 IC

### Things you will need in future updates

- A BL-5C battery
- Disassemble-able battery connecting wire
- (Optional) LED bar graph display
- (Optional) 4 Resistors for ↑

---

Everything here are basically all referenced to the official document. You can check out [references.md](./references.md) for more detailed information.\
The order of references in the file should be in chronological order of use.

---

# History

Latest first

### FUNCTION COMPLETED

On **117th build**(2026 Jan. 5 → 6 Midnight) WIRED FUNCTION COMPLETED!  
Turns out the real problem is I shouldn't make MISO (D9) a `CS` (AKA `latch`) pin while using SPI.  
**REMEMBER EVERYONE!** or you'll waste a whole lot of time.

On **107th build**(2026 Jan. 5) I finally make 74595-added version passed building.  
Need to be configure more to make it able to function normally, but it passed and basically runnable.  
Everything's finally going to reach a stage of an end…

### ZMK Studio function added successfully

On **85th build**(2025 Dec. 26) I finally added ZMK Studio successfully  
Okay, so every problem is from the `chosen` node in the [.dtsi](./boards/shields/zmk_4x3test/zmk_4x3test-layouts.dtsi) file. It's really "the chosen node"

### Clarified Column and Row

On **66th build**(2025 Nov. 11) I finally found that I misunderstand the meaning of column and row.  
As a little note, I'm going to make a note here

＼|Column 0|Column 1|Column 2
--|--------|--------|--------
Row 0|RC(0,0)|RC(0,1)|RC(0,2)
Row 1|RC(1,0)|RC(1,1)|RC(1,2)

### First successful build

Finally built successfully built on **51th build**, and realized it on **54th build**.  
The reason I'm not realized right when succeeded is that I was using my Samsung Galaxy Tab S7 FE + [VS code web version](https://vscode.dev), and it was laggy, so it's hard to see the progress with a very real-time experience.
