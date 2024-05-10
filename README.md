# Cura-Anet_A8_Bed_Logo
How to create a logo on your 3D printer bed when using Cura. Note: The logo will not print as part of your model.

Add Logo to ANet A8 3D Printer

1) Place new mesh (STL) (220x220x3 - 2.8) in:
C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\meshes

Edit Anet_A8_220x220.stl in cura to set offsets to X=0, Y=0, Z=-2.8mm to be adjoining the bed.
Export to: C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\meshes\net_A8_220x220.stl

2) Edit Printer definition file:
2A) C:\Program Files\UltiMaker Cura 5.2.2\share\cura\resources\definitions\anet3d_a8.def.json and
edit contents to
************************************************
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
************************************************
User Configuration folder
************************************************
2B)Copy anet3d_a8.def.json file from 2A to C:\Users\xxxxx\AppData\Roaming\cura\5.2\definitions\anet3d_a8.def.json

3) Edit Printer Definition Confifuration file @ C:\Users\xxxxx\AppData\Roaming\cura\5.2\definition_changes\Anet+A8+xxxxxx_settings.inst.cfg to
definition = anet3d_a8

4) Edit desired global configuration file @ C:\Users\xxxxx\AppData\Roaming\cura\5.2\machine_instances\Anet+A8+xxxxxx.global.cfg to
************************************************
[containers]
ooo
7 = anet3d_a8
************************************************
