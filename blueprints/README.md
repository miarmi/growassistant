# Modular VPD Control Blueprints

This folder contains three blueprints designed to work together:

1. `vpd_decider.yaml` — reads VPD/Temp/Humidity and writes one of `dehumidify | humidify | normal` into an `input_select` you provide.
2. `vpd_ac_controller.yaml` — sets AC to DRY when mode is `dehumidify`, otherwise AUTO with target temperature.
3. `vpd_humidifier_controller.yaml` — turns the humidifier ON when mode is `humidify`, OFF otherwise.

## Setup steps
1. Create an `input_select.vpd_mode` helper with options: `dehumidify, humidify, normal`.
2. Import all three blueprints.
3. Create three automations using each blueprint and wire the same `input_select.vpd_mode` into all of them.
4. Provide your AC (`climate`) and humidifier (`switch`) entities to the controllers.
5. Optionally enable notifications inside the controllers.

Keep the original monolithic `vpd.yaml` if you prefer, or switch entirely to the modular set.


