# Modular VPD Control Blueprints

This folder contains three blueprints designed to work together:

1. `vpd_decider.yaml` — reads VPD/Temp/Humidity and fires a `vpd_mode` event with `mode` in `dehumidify | humidify | normal`.
2. `vpd_ac_controller.yaml` — listens for the `vpd_mode` event and sets AC to DRY in `dehumidify`, otherwise AUTO with target temperature.
3. `vpd_humidifier_controller.yaml` — listens for the `vpd_mode` event and turns the humidifier ON in `humidify`, OFF otherwise.

## Setup steps
1. Import all three blueprints.
2. Create three automations (no helpers needed).
3. Provide your AC (`climate`) and humidifier (`switch`) entities to the controllers.
4. Optionally enable notifications inside the controllers.

Keep the original monolithic `vpd.yaml` if you prefer, or switch entirely to the modular set.


