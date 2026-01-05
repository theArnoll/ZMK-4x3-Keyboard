# References

In chronological order of use (basically)

[New Keyboard Shield](https://zmk.dev/docs/development/hardware-integration/new-shield?keyboard-type=unibody&physical-layouts=studio&interconnect=seeed_xiao)

[build.yml, ...](https://zmk.dev/docs/development/module-creation)

[Similar Keyboard in official repo](https://github.com/zmkfirmware/zmk/blob/main/app/boards/shields/boardsource3x4/)

[&studio_unlock in keymap](https://zmk.dev/docs/keymaps/behaviors/studio-unlock)

[.zmk.yml](https://zmk.dev/docs/development/hardware-integration/hardware-metadata-files)

[physical layout](https://zmk.dev/docs/development/hardware-integration/physical-layouts)

ZMK Studio:  
[Adding ZMK Studio Support to a Keyboard](https://zmk.dev/docs/features/studio#adding-zmk-studio-support-to-a-keyboard)  
[Physical Layout with `keys`](https://zmk.dev/docs/development/hardware-integration/physical-layouts#physical-layout-with-keys-example)

74595:
[74595](https://zmk.dev/docs/development/hardware-integration/shift-registers)  
[Pinout, SPI, I²C and Pin control file (For Seeed XIAO, nRF52840)](https://zmk.dev/docs/development/hardware-integration/pinctrl?interconnect=seeed_xiao&controller-type=nrf52840#boards-shields-and-modules) (Basically read it for the pinout of XIAO in the 74595 developing stage)  
Community Searching:
Googled [ZMK Shift register](https://www.google.com/search?q=ZMK+Shift+register) and found [this community .overlay and repo refrence](https://github.com/petejohanson/revxlp-config/blob/main/config/boards/shields/revxlp/revxlp.overlay#L12) from [this PR comment in zmk repo](https://github.com/zmkfirmware/zmk/pull/1325#issuecomment-1145555954) saw from [this one](https://github.com/zmkfirmware/zmk/issues/927#issuecomment-1166185627)

## To be use

[USB/Bluetooth toggle keycode](https://zmk.dev/docs/keymaps/behaviors/outputs)

[Using Bluetooth Output With USB Power](https://zmk.dev/docs/troubleshooting/connection-issues#using-bluetooth-output-with-usb-power)

[Debouncing](https://zmk.dev/docs/features/debouncing)

[(Maybe) Supported Handware](https://zmk.dev/docs/hardware#seeed_xiao)

## I remember I read it, but I forgot when

[Basic Physical Layout / Writing a position map](https://zmk.dev/docs/development/hardware-integration/physical-layouts#writing-a-position-map)  
for [`.dtsi` >](./boards/shields/zmk_4x3test/zmk_4x3test-layouts.dtsi) `/` > `position_map { layout1: layout1 { positions = <...>, <...>, ...; }; };`  
Point: `positions = <...>, <...>, ...;`