# Rush SR AiM Configurations

Pre-built AiM RaceStudio 3 configurations for Rush SR vehicles. Download the latest release below — each config is ready to import into RS3 and transmit to your dash or SmartyCam.

**[Download Latest Release](https://github.com/Rush-Auto-Works/aim-config-releases/releases/latest)**

## Which Config Do I Need?

| Your Dash | Throttle Cable? | Config |
|-----------|----------------|--------|
| MXS 1.2 (square, 6 LEDs) | No (DBW) | **Rush SR MXS v1.x DBW** |
| MXS 1.2 (square, 6 LEDs) | Yes (KLine) | **Rush SR MXS v1.x KLine** |
| MXS v2 (newer, rounded) | No (DBW) | **Rush SR MXS v2 DBW** |
| MXS v2 (newer, rounded) | Yes (KLine) | **Rush SR MXS v2 KLine** |
| MXM (no display) | No (DBW) | **RUSH SR MXM DBW** |
| MXM (no display) | Yes (KLine) | **RUSH SR MXM KLine** |

**Not sure if you have KLine or DBW?** If your car has a physical throttle cable, it's KLine (2021–early 2023 builds). If your data channels show names starting with "SDS" (Suzuki Diagnostic System), that's also KLine. All other cars are Drive-by-Wire (DBW).

SmartyCam configurations (SmartyCam 3 GP, SmartyCam 3 Dual, SmartyCam GP HD 2.2) are also included in each release.

## How to Install

1. Download the `.zconf2` file for your dash from the [latest release](https://github.com/Rush-Auto-Works/aim-config-releases/releases/latest)
2. Open **RaceStudio 3** on your computer ([download RS3](https://www.aim-sportline.com/en/sw-fw-download.htm) if you don't have it)
3. Go to **Configurations** in the left sidebar ([RS3 configuration docs](https://www.aim-sportline.com/docs/racestudio3/manual/html/configuration.html?highlight=export#list-of-configurations))
4. Click **Import** and select the downloaded `.zconf2` file
5. Open the imported configuration to review it
6. Connect your dash via USB and click **Transmit** to send it to the dash

## What's Included

Every Rush SR config comes pre-configured with:

### Channels & Sensors
- Engine RPM, water temperature, oil pressure, oil temperature
- Front and rear brake pressure (calibrated for 1000psi sensors)
- GPS speed, lap time, lateral/inline/vertical acceleration
- Gear position, throttle position, fuel level
- Battery voltage

### Math Channels
- **Brake Bias** — front/rear brake pressure ratio
- **Brake Perc** — brake load as a percentage
- **RPM OilP Ratio** — oil pressure as a percentage of what's expected for the current RPM. Since oil pressure scales with engine speed, a raw PSI number alone doesn't tell you much — 20 psi at idle is fine, but 20 psi at 8000 RPM is a serious problem. This channel normalizes pressure against RPM so you can spot issues at a glance. Values above 100% are healthy (expect 500–700% on a cold start, ~200% heading out for an outlap). Below 100% means pressure is lower than expected and the dash will start alerting. This channel also drives the **Check Oil Fill** and **Check Oil Pump** alarms.
- **OilP Mult** — oil pressure multiplied for display scaling

### Safety Alarms
Alarms display warning text on screen and blink the dash LEDs:

| Alarm | Condition | What to Do |
|-------|-----------|------------|
| Low Oil Pressure | Oil pressure dangerously low | Come in immediately |
| High Water Temp | Coolant > 230°F | Reduce pace, come in soon |
| Very High Water Temp | Coolant > 238°F | Come in immediately |
| High Oil Pressure | Oil pressure > 90 psi | Monitor — may indicate cold oil |
| Very High Oil Pressure | Oil pressure > 120 psi | Come in, check relief valve |
| Check Oil Pump | Continuous low pressure vs RPM | Come in, inspect oil system |
| Check Oil Fill | Pressure loss in hard corners | Add ~0.25L of oil |
| OilP Sender Failed | Sensor reading out of range | Check wiring/sensor |

### Dash Display
- Primary page with engine vitals and lap time
- Info line with brake pressures, oil pressure, water temp, and RPM OilP Ratio
- Shift lights calibrated for GSX-S1000 powerband

### SmartyCam Video Overlay
- Channel assignments for brake pressure, throttle, oil pressure, speed, and more
- Ready for video overlay rendering in RS3

## Merging Configurations

Already have a config with your own customizations? Use the **[AiM Config Merge Tool](https://rushautoworks.com/aim-config-merge/)** to merge the latest Rush alarms, math channels, and sensor definitions into your existing configuration without losing your personal settings.

## More Information

- **[Rush SR Owner's Manual](https://manual.rush.sr)** — full vehicle documentation
- **[Understanding Your Dash](https://manual.rush.sr/getting-started/understanding-your-dash)** — dash pages and controls
- **[Dash Alarms Reference](https://manual.rush.sr/maintenance/dash-alarms)** — complete alarm threshold table
- **[AiM Dashes & SmartyCams](https://manual.rush.sr/aim-dashes-and-smartycams)** — AiM hardware overview
- **[RaceStudio 3 Configuration Docs](https://www.aim-sportline.com/docs/racestudio3/manual/html/configuration.html)** — RS3 import/export guide
- **[Rush Auto Works Driver Toolbox](https://rushautoworks.com/driver-toolbox/)** — merge tool, telemetry converter, and more

## Questions?

Reach out on the [Rush SR Forums](https://rush.sr) or contact [Rush Auto Works](https://rushautoworks.com/contact/).
