# FLSUN S1
Improved configuration files for FLSUN S1

![Banner](https://github.com/user-attachments/assets/a2ebd6cd-e430-4d7b-a240-a8cac461b0c7)

## WARNING

- You need to redo all calibrations before printing when using this configuration files. To do this, run these macros in this order:
   - `CALIBRATE_MOTOR` to start Motors Calibration
   - `BED_LEVEL_1` to start Delta Calibration, after Klipper restart Bed Leveling will be runned automatically
   - `MEASURING_RESONANCES` to start measuring Resonances
 
## WHAT’S NEW IN THE IMPROVED VERSION?

- Reorganizing configuration files for clarity.
- Added `M600` functionality (hotend heating stopped after 15min of inactivity).
- Added support for `M106 P3 Sxx` to control Chamber Fan with OrcaSlicer.
- Added `LASER_CALIBRATION` macro.
- Added `PID_BED` and `PID_HOTEND` macros.
- Improved Bed Mesh.
- Improved resonance measurement, measurements are now carried out over the entire range from 1 to 133Hz instead of 20Hz to 80Hz.
- Improved `BED_LEVEL_1` and `BED_LEVEL_2` macros to allow user to choose the temperature of bed and hotend for Delta Calibration and Bed Leveling, by default hotend is set to 140C° and bed to 60C° (only on Web-UI not from the screen).
- Fixed `UNLOAD_FILAMENT` macro to heat nozzle to 240C° by default (or choose hotend temp from macro) and purge filament before retraction to avoid clogging.
- Fixed filament sensor detection. The pause was carried out as soon as the detector was triggered, which caused a significant loss of filament (approximately 600/650mm).
- Fixed the limitation of Z-Offset. It could only be applied in the range .02 to .05 (only on Web-UI not from the screen).
- Fixed `CANCEL_PRINT` macro to prevent the hotend from hitting drying box when print is cancelled and hotend is placed at the front of the bed.
- Other minor fixes.

## CHANGELOG

- **21/07/2024:**
  - Updated configuration files for firmware 1.0.4.4.

## NEEDED TO TEST

- `M600` functionality.
- Try lower arc resolution like 0.1 (to see if the machine will be able to support a lower resolution without to crash due to its low RAM).
