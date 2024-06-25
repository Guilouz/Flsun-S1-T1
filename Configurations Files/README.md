# FLSUN S1
Improved configuration files for FLSUN S1

![1717481915912_S1_banner](https://github.com/Guilouz/Flsun-S1/assets/12702322/9e41a6b0-dbc6-4a94-a95f-e4d0dd13ed8c)
 
## WHAT’S NEW IN THE IMPROVED VERSION?

- Reorganizing configuration files for clarity.
- Added M600 functionnality (Needed to test it).
- Added support for `M106 P3 Sxx` to control Chamber Fan with OrcaSlicer.
- Added `LASER_CALIBRATION` macro.
- Improved Bed Mesh.
- Fixed `UNLOAD_FILAMENT` macro to purge filament before retraction to avoid clogging.
- Fixed filament sensor detection. The pause was carried out as soon as the detector was triggered, which caused a significant loss of filament (approximately 600/650mm).
- Other minor fixes.

