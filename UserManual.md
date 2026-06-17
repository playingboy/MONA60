## Kit Includes:

1. **Enclosure:** Top mount structure with embedded brass threaded inserts and a precision CNC-machined ABS chassis.
2. **PCB:** Standard HHKB layout featuring a mainstream 6.25u spacebar. It comes hot-swappable (no soldering required) and supports both 5-pin and 3-pin switches. Powered by ZMK firmware, it features dual-mode BLE (Bluetooth Low Energy) and USB connectivity. BLE supports multi-device pairing, various RGB effects, fully customizable keymaps, mouse emulation, and an auto-sleep mode to conserve power.
3. **Integrated Display:** Features a small OLED screen that displays connection status, active layers (compact layouts rely on multiple layers), precise battery capacity, and your real-time typing speed (WPM).
4. **Type-C Daughterboard:** Equipped with an onboard overcurrent protection chip for enhanced safety. The daughterboard connects to the main PCB via a secure wire connector, allowing for a more aesthetically pleasing flush exterior port.
5. **Screen Cover:** Crafted from premium high-transparency acrylic material.
6. **Switch Plate:** Made of high-quality carbon fiber, which delivers a crisper acoustic profile and perfectly complements the top mount structure.
7. **Stabilizers:** PCB-mount (screw-in) stabilizers secured with brass pillars for maximum stability, significantly reducing rattling and ticking on large keys.
8. **Matching Hardware:** 304 stainless steel screws that resist rust and oxidation. Includes specialized washers to dampen housing resonance and optimize the typing sound.
9. **Battery:** A 2000mAh battery pack is included. Due to the high energy efficiency of the hardware design, a massive battery is unnecessary.
10. **Case Foam:** Premium Poron plate foam (not cheap standard foam) for superior acoustic dampening.
11. **Cable:** Includes a 2-meter Type-C data and charging cable.

---

## Operating Instructions:

1. **Connection Modes:** For wired mode, simply connect the keyboard via the Type-C cable to start typing. For Bluetooth mode, search for **MONA60** on your host device and pair. The leftmost column on **Layer 3** controls Bluetooth functions:
   * **ESC:** Clear active Bluetooth bond profiles.
   * **TAB:** Switch to Bluetooth Device 1.
   * **Control:** Switch to Bluetooth Device 2.
   * **Left Shift:** Switch to Bluetooth Device 3.
   * **Left Option (Win):** Switch to Bluetooth Device 4.
   * *Tip: Refer to the built-in screen to check your current connection status.*
2. **RGB Controls:** Press `Code(.)` + `Spacebar` to toggle the RGB underglow/backlighting on and off.
3. **Rear Switches:** Double-click the orange button to enter Bootloader mode. Below it are 3 DIP switches:
   * **(1):** RGB Hardware Power
   * **(2):** Battery Power Supply
   * **(3):** Battery Charging Circuit
   * *Usage Recommendations:* With a battery installed for daily wireless use, keep all 3 switches **ON**. Turn switch **(2) OFF** for long-term storage. If you run the board without a battery (wired-only mode), turn switches **(2)** and **(3) OFF**. Turn switch **(1) OFF** if you never use RGB to maximize battery life.
4. **Key Remapping:** In USB wired mode, you can customize your keymaps directly via the web configurator at [https://zmk.studio/](https://zmk.studio/). Once connected, the tool lets you visualize and modify the layout configurations for every single layer.
5. **Layer Layout:** The keyboard features 3 default layers. **Layer 1** (Base) handles your daily alphanumeric typing. **Layer 2** maps essential navigation and function keys. **Layer 3** houses Bluetooth controls, mouse emulation, and lighting adjustments. RGB lighting behavior (Hue, Saturation, Brightness, and Effects) can be fine-tuned using the clustered adjustment keys (`R`, `F`, `T`, `G`, `Y`, `H`, `U`, `G`, `\`). Feel free to experiment to find your perfect lighting style.

---

## Flashing Firmware:

1. Double-click the orange button on the back of the case twice to enter **Bootloader mode**.
2. The keyboard will mount to your computer as a mass storage USB drive named **MONA60**. Drag and drop or paste your prepared firmware `.uf2` file directly into this folder.
3. Firmware files can be downloaded directly from the GitHub Actions tab of the repository; there is no need to compile the source code yourself.

---

## Bootloader Interface (Advanced):

```bash
openocd -f interface/jlink.cfg -c "transport select swd" -f target/nrf52.cfg -s tcl;
```
