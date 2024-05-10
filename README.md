# Cura-Anet_A8_Bed_Logo
How to create a logo on your 3D printer bed when using Cura. Note: The logo will not print as part of your model.

Add Logo to Cura Anet A8 3D Printer

1) Place STL (220x220x3) in:
C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\meshes\Anet_A8_220x220.stl

save as -2.8mm to be adjoining the bed.

2) Edit Printer definition file to include stl: where xxxxx is your user account @
2.a) C:\Program Files\UltiMaker Cura 5.7.1\share\cura\resources\definitions and @
2.b) C:\Users\xxxxx\AppData\Roaming\cura\5.7\definitions\anet3d_a8.def.json
{
    "version": 2,
    "name": "Anet A8",
    "inherits": "anet3d",
    "metadata": {
        "visible": true,
	"has_machine_materials": true,
        "platform": "Anet_A8_220x220.stl",
        "platform_offset": [ 0, 0, 0 ],
        "machine_extruder_trains": { "0": "anet3d_extruder_0" }
    },

    "overrides": {
        "machine_name": { "default_value": "Anet A8" },
        "machine_width": { "default_value": 220 },
        "machine_depth": { "default_value": 220 },
        "machine_height": { "default_value": 240 },
        "machine_start_gcode": { "default_value": "G28 ;Home\nG1 Z15.0 F2000 ;Move the platform" },
        "machine_end_gcode": { "default_value": "M104 S0\nM140 S0\nG92 E0\nG1 E-10 F2000\nG28 X0 Y0\nM84"}
    }
}

3. Edit Machine Instance File:
C:\Users\xxxxx\AppData\Roaming\cura\5.7\machine_instances\Anet+A8+Glass+Bed.global.cfg
[containers] should be
7 = anet3d_a8
