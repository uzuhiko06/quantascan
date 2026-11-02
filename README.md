# QuantaScan

A magnetic X-ray for EV battery packs. QuantaScan uses NV-diamond quantum magnetic sensing to find bad welds and shorted cells inside a battery module without opening it.

**Live demo:** https://uzuhiko06.github.io/quantascan/

**Important:** all data in this MVP is simulated. This is a software model of the inspection pipeline. The quantum sensor hardware is not built yet (concept stage, TRL 2).

## What the MVP does
- Models a 24-cell battery module (4 rows by 6 cells).
- Injects a fault: weak weld, open weld or cell short.
- Simulates the magnetic image a sensor would see, with adjustable sensor noise.
- Detects the fault, locates the faulty cell and gives a PASS/FAIL result.
- Shows how good the sensor must be to detect the fault reliably.

## How it works
Each cell's connection strip is modelled as a straight wire carrying a test current. The magnetic field above the pack is computed with the Biot-Savart law at 3 mm standoff, with 1.5% natural cell-to-cell variation. The scan fits one current value per cell to the measured image and flags any cell that deviates by more than the larger of 8% or four times its noise-limited uncertainty.

## Limitations
This is a simplified model for a concept-stage demo, not a validated pack simulation. Results depend on assumptions such as test current, sensor distance and cell layout.

## Next steps
- Bench-test magnetic sensing on a real cell or module.
- Validate the model against measured data.
- Work with a pack manufacturer or testing lab to define real inspection requirements.

## Run locally
Open `index.html` in any browser. No installation needed.

Built for Indiathon 2026 by [Sahithi siva].
