# 🚀 BACKFIRE — Planned Improvements & Roadmap

## 1. Multiplayer & Networking Enhancements
- [ ] **Full 2v2 Arena Matchmaking**:
  - Extend PeerJS mesh/star topology to handle 4 concurrent pilots in a room.
  - Team assignments: Blue 1 & 2 vs Red 1 & 2 with distinct pilot accent colors.
  - Roster scoreboard reflecting all 4 pilots and team respawn states.
- [ ] **State Interpolation & Lag Compensation**:
  - Hermite curve / cubic spline interpolation between received position packets (~30Hz) for buttery-smooth 60-120fps visual tracking.
  - Client-side prediction for hit detection so high-ping matches maintain sharp shot feedback.
- [ ] **Host Migration & Fallback Signaling**:
  - If the host drops, elect the next connected peer as host without resetting scores.
  - Multi-server STUN/TURN fallback configuration for restrictive NAT firewalls.
- [ ] **In-Game Ping & Network Stats HUD**:
  - Live round-trip time (RTT) latency display in milliseconds next to the match tag.

---

## 2. Combat Mechanics & "Juice"
- [ ] **Momentum Multiplier (Speed = Damage)**:
  - Scale knockback force by current velocity: hitting an enemy while rocketing at >25 m/s deals double kinetic impulse.
  - Visual speed lines / dynamic camera FOV expansion (75° → 95°) when hitting super-sonic velocities.
- [ ] **Harpoon Slingshot & Enemy Whiplash**:
  - Ability to grapple an enemy and violently flick the mouse to "slingshot" them into hazards.
  - Harpoon line tension snapping effect with audio recoil when exceeding elastic limit.
- [ ] **Melee Kinetic Stomp**:
  - Pressing `Space + Look Down` while airborne triggers a shockwave ground-pound, blasting nearby pilots into the air.
- [ ] **Directional Hazard Warning Indicators**:
  - Edge-of-screen warning arrows pulsing red when flying backward toward molten pit or spike walls.

---

## 3. Audio & Visual Polish
- [ ] **3D Spatial Audio**:
  - Upgrade Web Audio oscillators with `PannerNode` positioned at 3D world coordinates for weapon bangs, turbine hums, and hazard crunches.
- [ ] **Custom Character Rigs & Animations**:
  - Articulated jetpack thrusters that emit directional flame particles based on active velocity vector.
  - Weapon viewmodel bobbing, sway, and muzzle flash light bursts on firing.
- [ ] **Knockout Replay / Spectator Cam**:
  - Brief 1.5s freeze-frame cinematic killcam focusing on the victim impacting the hazard.
  - Post-match MVP summary (Top Speed, Hazard Kills, Longest Harpoon Pull).

---

## 4. Map & Environmental Dynamics
- [ ] **Interactive Hazard Triggers**:
  - Shooting the turbine central axle temporarily accelerates the blades to double RPM for 3 seconds.
  - Shooting the molten pit core causes a lava flare that knocks airborne players away.
- [ ] **Destructible Arena Cover**:
  - Concrete barrier blocks that fracture and shatter when pilots are slammed into them at high velocity.
- [ ] **Multiple Arena Layouts**:
  - **Map 2: The Core** — Vertical cylinder with ascending gravity lifts and ceiling spikes.
  - **Map 3: Zero-G Orbit** — Low-gravity spherical cage with 360-degree hazard perimeter.

---

## 5. UI, Customization & Quality of Life
- [ ] **Settings Modal**:
  - Mouse sensitivity slider.
  - Inverted Y-axis toggle.
  - Master audio & SFX volume sliders.
  - Graphics toggle (Shadows On/Off, Particle density).
- [ ] **Pilot Customization**:
  - Armor color picker & custom visor glow styles.
  - Custom death tag lines (e.g., "[Player] was fed to the turbine").
- [ ] **Mobile / Touchscreen Support**:
  - Dual virtual thumbsticks and touch fire buttons for browser mobile testing.
