# Choc Half ZMK firmware

ZMK configuration for one standalone Corne 5-column left half using a
nice!nano-compatible controller.

There is no dongle and no display. The complete two-half Corne keymap remains
in `config/corne.keymap`, so its physical positions and layers can still be
edited as a normal full Corne layout. Only the left-half firmware is built and
used; right-half key positions are simply unavailable while no right half is
connected.

## Firmware artifacts

Every GitHub Actions build produces exactly two firmware artifacts:

- `corne_left`: normal firmware for the left half.
- `settings_reset`: clears ZMK settings and Bluetooth bonds on the controller.

## Flashing

For a normal update, copy `corne_left.uf2` to the controller's UF2 drive.

To clear old settings, flash `settings_reset.uf2` once, let the controller
restart, then return it to the bootloader and flash `corne_left.uf2`.

On the base layer, holding `Q + W + E + R + Space` enters the bootloader.
