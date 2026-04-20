# 🚁 Drone Viz

**32 phase-stepped visualizers for drone subsystems.** From motor mixing to Kalman filters — each concept rendered as an animated phase-stepped diagram where variables, signals, and hardware all change together.

Part of the **Workshop-DIY** visualizer family:
- 🚁 [drone-viz](https://github.com/abourdim/drone-viz) — drones (you are here)
- 🛠️ [maker-viz](https://github.com/abourdim/maker-viz) — 17 sensors/motors vizzes
- ⚡ [electro-viz](https://github.com/abourdim/electro-viz) — 70 electronics foundations

## Live demo

👉 **[abourdim.github.io/drone-viz](https://abourdim.github.io/drone-viz/)**

## What's inside

### ⭐ Top 5 — must-ships
| Viz | What you learn |
|---|---|
| [Motor Mixer](motor-mixer.html) | 4 sticks → 4 motor speeds. The foundation. |
| [Flight Control Stack](fc-stack.html) | 6-stage pipeline from stick flick to motor spin |
| [Failsafe FSM](failsafe-fsm.html) | ARMED → FLYING → RTH. The logic that saves drones |
| [PID Dance-Off](pid-dance.html) | 3 tunes race to setpoint — tuning intuition live |
| [Gyro LPF Chain](gyro-lpf.html) | 4 filters kill noise stage-by-stage |

### All 32 — organised into categories
- **Control &amp; Mixing** — flight-modes, airmode
- **Motors / Power** — thrust-curve, prop-balance, esc-protocols, battery-sag
- **Sensors &amp; Fusion** — altitude-hold, gps-glitch, optical-flow
- **Aerodynamics** — aoa-stall, propwash, wind-gps, ground-effect
- **Safety** — arming-checks, crash-detector
- **Navigation** — waypoint, rth, geofence
- **FPV &amp; Video** — latency, analog-digital, race-gate
- **Telemetry / Logs** — blackbox, osd
- **Exotic machines** — tricopter, swashplate, vtol, gimbal

## How to use

1. Open `index.html` (or the live demo link).
2. Pick a visualizer card.
3. Press **STEP** for one phase, **PLAY** for auto-loop.
4. Speed slider for slow-mo analysis.
5. Per-viz sliders change inputs live.

## Architecture

Every visualizer is **one self-contained HTML file** on a ~200-line shared engine. State + phases + stage SVG + code lines → automatic stepper with play/pause/reset, variable flash animations, active-line highlighting, and narration.

```js
MakerViz.create({
  vars:   { ... },
  phases: [ ... ],
  lines:  [ ... ],
  stage:  (state) => svgString,
  run:    (phase, state, ui) => { ... }
});
```

## Workshop-DIY template

Gallery index uses the [Workshop-DIY](https://github.com/abourdim/tools) template: splash, bismillah header, 9 themes (Space default for the drone vibe), trilingual i18n, activity log, easter eggs.

## Run locally

```bash
python -m http.server 8000
# http://localhost:8000
```

## License

MIT — see [LICENSE](LICENSE).
