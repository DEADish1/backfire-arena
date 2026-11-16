# 🔥 BACKFIRE — Master Feature & Development Checklist

This master checklist tracks everything built so far and all remaining features planned for **BACKFIRE**.

---

## 🟢 1. Core Arena & Production (Completed & Live)
- [x] **Persistent Vercel Deployment**: Live production URL at [`https://backfire-arena.vercel.app`](https://backfire-arena.vercel.app)
- [x] **Zero-Server P2P Networking**: WebRTC DataChannels using PeerJS with public STUN signaling
- [x] **Instant Room Link Sharing**: Auto-generated room codes (`?room=BF-XXXX`) and one-click clipboard copying
- [x] **Offline Practice Arena**: Single-player combat duel against a Newtonian physics AI bot
- [x] **Newtonian Weapon Recoil Physics**: 3 distinct zero-damage weapons (Breaker 12G, Jackhammer, Rail Slugger) where weapon thrust is the primary movement mechanic
- [x] **Lethal Environmental Hazards**: North/South spike walls, West rotary turbine shredder, Center molten lava pit, 4 corner jump pads

---

## 🟢 2. Graphics, Audio & Combat Juice (Completed & Live)
- [x] **ACES Filmic Tone Mapping**: Film-grade color contrast (`exposure: 1.18`) with `sRGBEncoding`
- [x] **2048px High-Definition Soft Shadows**: Crisp directional sun shadows with PCF soft filtering
- [x] **Procedural Sci-Fi Textures & Bump Maps**: Brushed slate-metallic floor tiles with corner rivets, glowing data conduits, and yellow/black hazard bulkhead chevron walls
- [x] **Animated Molten Lava & Heat Radiance**: Procedural churning magma veins with organic oscillating point light flicker
- [x] **Dynamic Real-Time Muzzle Flash**: Camera point light that flashes and illuminates arena walls on every shot
- [x] **Atmospheric Floating Embers**: 140 glowing amber motes with upward convection drift
- [x] **Studio Audio Engine with Dynamics Compressor**: Web Audio limiter preventing harsh distortion and digital clipping
- [x] **Browser Audio Auto-Resume**: Global capture listeners ensuring audio never gets stuck in a browser "suspended" state
- [x] **Multi-Layered Procedural Sound Design**: Sub-bass kinetic sweeps, shaped noise bursts, mechanical pump clacks, and weapon switch clicks
- [x] **Dynamic FOV Velocity Warping**: Camera FOV expands smoothly from 75° to 92° at supersonic speeds
- [x] **Kinetic Momentum Slam Multiplier**: High-speed collisions deliver up to 2.5× concussive knockback force
- [x] **Harpoon Slingshot & Enemy Whiplash**: Reciprocal physical tension on latched opponents with dynamic tension color changes
- [x] **Air-Brake Shockwave Stomp**: Pressing `Space + Down` in mid-air slams vertically (-42 m/s) and emits a 360° expanding energy shockwave ring on the floor
- [x] **Directional Hazard Trajectory Warnings**: 1.3-second predictive vector HUD badge alerting to imminent hazard collisions
- [x] **3D Spatial Audio**: Stereo azimuth panning and distance attenuation for remote gunshots and impacts
- [x] **Hermite/Lerp State Interpolation**: 60–144Hz smoothing for remote pilots eliminating network jitter
- [x] **Scoring Bug Fix & Debouncing**: Single-event protection, collision suspension during the 1.0s respawn window, and stabilized camera shake

---

## 🟡 3. Multiplayer & Networking (Pending)
- [ ] **2v2 Full Mesh Team Matchmaking**:
  - Support for 4 concurrent pilots in a room (Blue 1 & 2 vs Red 1 & 2)
  - 4-pilot scoreboard with team-colored HUD indicators and active respawn timers
- [ ] **Host Migration Failover**:
  - Automatically elect the next peer if the host leaves without resetting match score
- [ ] **Auto-Reconnect & State Recovery**:
  - Smooth reconnection if a player's Wi-Fi briefly drops without kicking them from the match
- [ ] **Quick Tactical Pings / Chat Wheel**:
  - Contextual pings (e.g., "Attack Turbine", "Watch Lava", "Spike Threat") using middle-mouse click

---

## 🟡 4. Combat Variety & Mechanics
- [x] **Alternate Fire Modes (`Q` or `Middle-Click`)**:
  - *Breaker 12G (Alt-Fire)*: Concussive Blast Wall (16-pellet horizontal arc, +44 m/s super-jump thrust)
  - *Jackhammer (Alt-Fire)*: Retro-Jet Hover Mode (anti-gravity downward thrusters holding pilot hovering in mid-air)
  - *Rail Slugger (Alt-Fire)*: Piercing Overcharge Beam (charges up and penetrates directly through concrete pillars)
- [x] **Core Weapon Heat Gauge & Supercharged Recoil**:
  - Real-time heat meter (0–100%) with dynamic passive cooling
  - At ≥75% heat, pilot enters **SUPERCHARGED** state gaining +25% bonus recoil thrust
- [x] **Destructible Arena Pillars & Physical Debris**:
  - The 4 concrete arena cover pillars have localized health pools and crumble into structural rubble when rammed by pilots at high velocity (>14 m/s) or blasted
  - Pillar destruction updates arena sightlines and synchronizes across the P2P network
- [ ] **Hazard Overload Combos**

---

## 🟡 5. Map & Arena Diversity
- [x] **Modular Arena Map Selector (In Lobby & P2P Synced)**:
  - Added real-time arena switcher between **Map 1: Hazard Foundry** and **Map 2: The Core**
- [x] **Map 2: "The Core" (Vertical Reactor Silo)**:
  - 44m-tall cylindrical reactor silo with dual floating ring catwalks (y = 11m & y = 24m)
  - Ceiling spike grid hazard (impales pilots launched too high)
  - Central 42 m/s anti-gravity lift beam shooting pilots skyward into aerial combat
  - Bottom molten plasma abyss
- [x] **Dynamic Arena Hazard Events (Synchronized)**:
  - **Lava Tide Surge**: Periodic emergency alarm elevates molten magma by +2m, flooding the central arena floor and forcing pilots airborne
  - **Turbine Suction Vortex**: High-powered turbine vortex pulls all airborne pilots toward the West shredder blades
- [ ] **Map 3: "Zero-G Orbit" (Spherical Cage Arena)**:
  - Spherical arena with full 360° orbital movement and perimeter hazard rings

---

## 🟡 6. Visual, Customization & Quality of Life
- [x] **3D Thruster Jet Plumes & Exhaust VFX**:
  - Animated glowing cyan cone exhaust meshes on remote opponent's backpack scaling in real-time with velocity (up to 1.6× length)
  - Directional thruster particle exhaust plumes on retro-jump, recoil thrust, and hover maneuvers
- [x] **Pilot Customization & Visor Color Palette**:
  - Interactive color picker (Cyan, Ruby Red, Emerald Green, Cyber Gold, Neon Violet) in the settings drawer
  - Dynamically updates crosshair energy, weapon conduit glow, and transmits across P2P network to opponent's 3D visor
- [x] **Post-Match MVP & Victory Stat Ceremony**:
  - Fullscreen victory celebration screen triggered on match completion (WIN_SCORE = 5)
  - Displays Max Velocity Reached, Total Hazard Pulverizations, Longest Harpoon Sling, and Stomp Impacts
  - One-click "PLAY AGAIN / REMATCH" instant match reset
- [x] **Fullscreen Quick Toggle**:
  - Dedicated `⛶ FULLSCREEN` button on top HUD
- [ ] **Keybinding Remap Menu**: Custom keyboard and mouse remapping in the Settings drawer
- [ ] **Touch / Mobile Joystick Support**: On-screen dual virtual thumbsticks for smartphone/tablet browser play

---

## 🟢 7. Infrastructure & Git Sync (Completed)
- [x] Local Git repository initialized on `main` with 10 feature commits
- [x] Remote GitHub repository linked and active at [`DEADish1/backfire-arena`](https://github.com/DEADish1/backfire-arena)
- [x] All source code, assets, procedural generators, and documentation pushed to `origin/main`
- [x] Production deployed and aliased at [`https://backfire-arena.vercel.app`](https://backfire-arena.vercel.app)
