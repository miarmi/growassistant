Modular VPD Control for Home Assistant

Contents
- blueprints/vpd_decider.yaml — computes mode (dehumidify/humidify/normal)
- blueprints/vpd_ac_controller.yaml — applies AC DRY/AUTO based on mode
- blueprints/vpd_humidifier_controller.yaml — toggles humidifier based on mode
- notification.yaml — generic notification blueprint (optional)

Setup
1. Create helper `input_select.vpd_mode` with options: dehumidify, humidify, normal
2. Import all blueprints in `blueprints/`
3. Create 3 automations, wiring the same `input_select.vpd_mode` to each
4. Provide your `climate` entity to the AC controller and `switch` to the humidifier controller
5. Optionally enable notifications in controllers

Notes
- The previous monolithic `vpd.yaml` was removed in favor of modular blueprints
