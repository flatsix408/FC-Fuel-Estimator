# Elite Dangerous Carrier Fuel Estimator

A small client-side web app to estimate fleet carrier Tritium consumption for jumps in Elite Dangerous.

Features
- Calculates fuel using the canonical formula:
  F = ROUND(10 + (D / 4) × (1 + (M + T) / 25000))
  where D = jump distance (ly), M = number of optional services, T = Tritium tonnage in depot.
- Calculates the simplified formula for when the depot is refilled after every jump:
  F = ROUND(10 + D × (0.26 + M / 100000))
- Provides an optional manual "Carrier Mass Adjustment (%)" slider so you can model the effect of total carrier mass (cargo, modules, Tritium weight) as a percent adjustment. There is no authoritative published mass multiplier for the formula, so this field lets you apply a user-defined percent change to the result.
- Lightweight single-file web UI (no build tools required).

How to use
1. Open `index.html` in a modern browser.
2. Enter jump distance (D, in ly), number of optional services (M), and Tritium depot tonnage (T).
3. Choose whether the depot is refilled after each jump (affects which formula is used).
4. Optionally adjust the "Carrier Mass Adjustment (%)" slider to apply a manual correction for mass effects.
5. The app displays the estimated fuel required and a short breakdown.

Notes
- The app intentionally implements the published formulas exactly (including the ROUND behavior).
- The mass adjustment is purely user-controlled and does not come from the published formula — use it to reflect cargo/modules/tritium mass influence based on your own experience.

Files
- index.html — the web UI and logic (single-file, includes all CSS/JS).

License
- Public domain / use as you like.