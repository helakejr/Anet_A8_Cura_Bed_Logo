# Cura-Anet_A8_Bed_Logo
How to create a logo on your 3D printer bed when using Cura. Note: The logo will not print as part of your model.

Add Logo to Cura Anet A8 3D Printer

1) Place STL (220x220x3 - 2.8) in:
C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\meshes
Anet_A8_220x220.stl

save as -2.8mm to be adjoining the bed.

2) Edit Printer definition file:
C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\definitions
anet3d_a8.def.json

************************************************
User Configuration folder
C:\Users\helak\AppData\Roaming\cura\5.2\definition_changes
Anet+A8+Glass+Bed_settings.inst.cfg
definition = custom -> definition = anet3d_a8
