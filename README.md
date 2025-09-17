Modular VPD Control for Home Assistant

Contents
- blueprints/vpd_decider.yaml — computes mode (dehumidify/humidify/normal)
- blueprints/vpd_ac_controller.yaml — applies AC DRY/AUTO based on mode
- blueprints/vpd_humidifier_controller.yaml — toggles humidifier based on mode
- notification.yaml — generic notification blueprint (optional)

Setup (event-driven, no helpers needed)
1. Import all blueprints in `blueprints/`
2. Create three automations (one per blueprint)
3. Provide your `climate` entity to the AC controller and `switch` to the humidifier controller
4. Optionally enable notifications in controllers
Note: The decider blueprint emits a `vpd_mode` event that the controllers listen to.

Notes
- The previous monolithic `vpd.yaml` was removed in favor of modular blueprints
