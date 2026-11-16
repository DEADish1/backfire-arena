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

## 🟢 2. Graphics, Audio & Bulletstorm Realism Overhaul (Completed & Live)
- [x] **Bulletstorm Map Overhaul & Realistic Industrial Aesthetic**:
  - **Sun-Drenched Stygian Lighting**: Harsh 2.3-intensity directional sunlight with warm baked rust/soil ambient bounce (`0x4a3628`) and high-contrast ACESFilmic tone mapping (`exposure: 1.30`)
  - **360° Atmospheric Stygia Sky Dome**: Procedural panoramic sky with glowing amber-orange horizon smog and distant ruined industrial refinery silhouettes
  - **Weathered Diamond-Plate Steel Floor**: High-detail embossed diamond treads, panel seams, hex bolts, rust bleeding, soot grime, and stenciled industrial warnings (`STYGIA SECTOR-04`, `DANGER: LIVE RAIL 50KV`)
  - **Battered Corrugated Bulkhead Walls**: Heavy concrete foundations, vertical rust water drippings, corrugated steel cladding, and bold yellow/black hazard chevron girders
  - **Multi-Layered Volcanic Molten Slag**: Boiling magma with incandescent white-hot fissure veins, turbulent orange currents, and floating cooling black iron slag crust islands
  - **Brutal Rebar Impalement Barricades (North & South)**: 48+ jagged, angled high-tensile steel construction rebar rods with barbed hooks and flashing red hazard strobe beacons
  - **Industrial Rotary Meatgrinder (West Wall)**: 11.5m circular cast-iron casing with protective steel intake bars, dual warning strobe beacons, toothed crusher cutter blades, and continuous friction sparks
  - **Bulletstorm Destructible Concrete Pillars**: Heavy square concrete pillars with aggregate pores, stress cracks, steel reinforcement collar bands, and exposed rebar studs
  - **Overhead Structural Gantry Trusses**: Massive rusty steel I-beam trusses spanning overhead at Y=16m casting high-res industrial cage shadows across the sun-drenched floor
  - **Industrial Hydraulic Jump-Pads**: Heavy-duty hazard-chevron pneumatic stomp plates with 4 corner steel coil springs and glowing cyan pressure vents
- [x] **Comprehensive High-Fidelity Graphics Overhaul (Tangent Normal Maps, God Rays & Mech Model)**:
  - **Procedural Tangent-Space Normal Maps & Roughness Maps**:
    - `createProceduralFloorNormalMap()`: Canvas-generated tangent-space normal maps calculating true height gradients for 3D diamond-plate steel treads, plate seams, hex bolt heads, and surface pits.
    - `createProceduralFloorRoughnessMap()`: Glossy specular hotspots on worn tread ridges with matte oxidized recess crevices.
    - `createProceduralWallNormalMap()`: Corrugated vertical sinusoidal relief and concrete seams for arena bulkheads.
    - `createProceduralConcreteNormalMap()`: Aggregate pores, stress fractures, and rebar seams for cover pillars.
  - **Soft Contact Shadows & Volumetric God Rays**:
    - PCF soft shadows with `radius = 2.2` and `normalBias = 0.04` eliminating shadow acne while preserving crisp contact depth.
    - `createGodRays()`: 6 angled volumetric light shafts filtering down through roof trusses with oscillating transparency.
    - `createAtmosphericDustMotes()`: 300 floating golden dust motes drifting with Brownian motion catching sunlight beams.
  - **First-Person Viewmodel Detailing & Procedural Animation**:
    - *Breaker 12G*: Perforated barrel heat shroud, holographic reflex sight frame with glowing green reticle, side shell saddle with 4 red 12-gauge shells with brass bases, and animated pump handle.
    - *Jackhammer*: Under-slung drum magazine with knurled grip, dual chrome reciprocating piston rods.
    - *Rail Slugger*: 4 magnetic stator acceleration rings with copper coils, digital charge readout, and dynamic crackling electric arc between rails.
    - *Procedural Weapon Sway & Bob*: Spring-damper mouse lag inertia and natural breathing/movement bobbing.
    - *Physical Ejected Shell Casings*: 3D brass casings with velocity, tumble physics, and arena floor bounce.
  - **3D Articulated Mech Pilot Actor**:
    - Angular faceted helmet with panoramic glowing visor, ear comm-pods, modular ballistic chestplate, glowing sternum reactor core, shoulder pauldrons, articulated arms holding a 3D tactical carbine, magnetic combat boots, and dual-turbine jetpack with animated exhaust flame plumes.
  - **Molten Bullet Impact Decals & Ricochets**:
    - Bullet hits on pillars/walls spawn glowing orange crater decals that cool to dark soot over 4.5s.
    - Volumetric 3D cylinder mesh bullet tracers with additive glow.
  - **3D Boiling Lava Bubbles & Film Grain**:
    - 14 rising magma bubbles in the smelter that expand and burst into spark embers.
    - Gritty Bulletstorm cinematic SVG film grain noise overlay.
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
- [x] **Production Stability & Rendering Fixes**:
  - Global scoping of arena dimension constants (`ARENA_HALF`, `ARENA_SIZE`) preventing first-frame render loop exceptions
  - Safe Pointer Lock promise rejection handling and guaranteed modal dismissal on match deploy
  - Multi-map hazard null safety guards (`lavaPit` assignment and dynamic hazard bounds checking)
  - Destructible pillar material color traversal handling Three.js Groups cleanly without runtime errors

---

## 🟢 3. Combat Variety, Scoring & Objective Rules (Completed & Live)
- [x] **Core Objective & Trap Avoidance Scoring Rules**:
  - **Zero Direct Weapon Damage**: Weapons act as pure recoil thrusters and kinetic concussive knockback tools; damage occurs exclusively through environmental traps.
  - **Hitting Traps Gives Other Team +1 Point**: When a pilot hits spikes, lava, or the meatgrinder, exactly 1 point is awarded to the opposing team (`victimTeam === 'blue' ? redScore++ : blueScore++`).
  - **Differentiated Knockout Feedback (Victim vs Killer)**:
    - *When Local Pilot Hits a Trap*: Flashes intense hazard red banner (`💀 YOU HIT A TRAP! +1 POINT TO OPPONENT`), triggers deep concussive crunch audio, violent screen shake (`0.85`), and red visor splatter. Zero celebratory skillshots awarded to the victim.
    - *When Opponent Hits a Trap*: Flashes glowing emerald victory banner (`💥 ENEMY HIT A TRAP! +1 POINT TO YOUR TEAM`), plays celebratory fanfare, triggers controller rumble, awards Bulletstorm Skillshot points, and spawns 3D world-space floating badges over the kill site.
  - **Persistent HUD Mission Goal Banner**:
    - Central badge under scoreboard: `🎯 GOAL: AVOID ALL TRAPS — HITTING A TRAP GIVES +1 PT TO OPPONENT (FIRST TO 5 WINS)`.
  - **Dynamic Scoreboard Team Identification**:
    - Labels show `BLUE (YOU) vs RED (BOT)` in solo practice, `BLUE (YOU) vs RED (ENEMY)` for host, and `BLUE (HOST) vs RED (YOU)` for guests.
  - **Lobby Start Modal Objective Card**:
    - High-visibility golden callout card detailing that hitting traps gives the opponent points and explaining the physics-only win condition.
  - **Map 1 Bridge Hazard Collision Fix**:
    - Safe traversal across the central steel crossing bridge over the molten slag pit without phantom lava collision triggers.
- [x] **Full Combat Overhaul & Kinetic Feedback**:
  - **Dynamic Crosshair Hitmarkers & Audio Ticks**: 4-tick rotated hitmarker with crisp audio synthesis (1850Hz standard / 2600Hz critical) confirming connected shots
  - **Opponent Hit Flash VFX**: High-contrast white/red emissive flash on opponent chassis upon kinetic impact
  - **Obstacle Line-of-Sight Raycasting**: Bullet raycaster checks against solid arena cover pillars and bulkheads before registering hits (except for the wall-penetrating Railgun Overcharge)
  - **Directional Incoming Damage Vignette Flash**: Red edge-screen vignette pulse alerting pilots to incoming opponent concussive impulses
  - **Active Tactical Combat AI Bot in Solo Mode**: Fully autonomous bot that circular-strafes, maintains 12–22m combat spacing, detects spike walls & lava pits to counter-thrust and rocket-jump away, selects weapons dynamically (Breaker Shotgun vs Rail Slugger), fires red tracers with line-of-sight checks, and applies physical concussive knockback with damage flash and screen shake when hitting the player
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
- [x] **Hazard Overload Combos & Bulletstorm Skillshots**:
  - **Turbine Suction Overload**: Shooting the rotary shredder spins blades to 28.0 RPM with amber sparks and draws in nearby pilots
  - **Molten Slag Geyser Eruption**: Shooting the central lava core launches a +22 m/s thermal geyser blast tossing pilots skyward
  - **50,000V Electrified Rebar Grid**: Shooting North/South spike walls triggers electric arcs and lethal electrocution
  - **Bulletstorm Skillshot Detection Engine**: 10+ cinematic kinetic skillshots awarding bonus match points ("VOODOO DOLL", "BARBED SKEWER", "MEAT SLICER", "SAUSAGE GRINDER", "SLIDE TRIPPED", "FLY SWATTER", "HIGH VOLTAGE", "MOLTEN TSUNAMI", "VORTEX PULVERIZE", "BOOT CAMP", "SKY BURIAL", "DAM BUSTER")
  - **Golden Skillshot Banner & MVP Ceremony**: Fullscreen golden pop-up banner with Web Audio fanfare, tracking the top skillshot award on the final MVP scoreboard

---

## 🟢 4. Map & Arena Diversity (Foundry, The Core & Stygia Dam)
- [x] **Modular 3-Map Selector (In Lobby & P2P Synced)**:
  - Real-time arena switcher between **Map 1: Foundry**, **Map 2: The Core**, and **Map 3: Stygia Dam**
- [x] **Map 1: "Foundry" (Stygia Industrial Smelter)**:
  - Sun-drenched scorched arena with diamond-plate floor, molten slag smelter, rotary meatgrinder, and rebar impalement barricades
- [x] **Map 2: "The Core" (Vertical Reactor Silo)**:
  - 44m-tall cylindrical reactor silo with dual floating ring catwalks with safety handrails (y = 11m & y = 24m)
  - Ceiling rebar impaler grid (impales pilots launched too high)
  - Central 42 m/s anti-gravity lift beam shooting pilots skyward into aerial combat
  - Bottom molten plasma abyss
- [x] **Map 3: "Stygia Dam" (Canyon Spillway Ruins)**:
  - High-altitude sun-drenched industrial dam overlooking a vast canyon ruin
  - Concrete dam wall with upper crest catwalk at Y=16m
  - Central hydro spillway molten runoff vat
  - Giant hydro-turbine grinder embedded in the dam face
  - South rebar impalement barricades and high-altitude pneumatic jump-pads
- [x] **Dynamic Arena Hazard Events (Synchronized)**:
  - **Lava Tide Surge**: Periodic emergency alarm elevates molten magma by +2m, flooding the central arena floor and forcing pilots airborne
  - **Turbine Suction Vortex**: High-powered turbine vortex pulls all airborne pilots toward the West shredder blades

---

## 🟢 5. Visual, Customization & Quality of Life
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
- [x] **Keybinding Remap Menu**: Custom keyboard and mouse remapping in the Settings drawer with localStorage persistence and interactive rebind listening
- [x] **Touch / Mobile Joystick Support**: On-screen dual virtual floating thumbstick and dedicated touch action buttons for smartphone/tablet browser play
- [x] **Bulletstorm Game Controls & Kinetic Mobility Overhaul**:
  - **First-Person Armored Boot Kick (`E` or `F` / Gamepad `X` or `R3`)**:
    - Animated 3D first-person armored combat boot thrust with cyan/amber sole treads
    - Delivers a brutal +36 m/s directional kinetic shove launching opponents into environmental hazards
    - Shatters destructible cover pillars within 2.5m and synchronizes over P2P network (`kick_shove`)
    - AI Bot can execute close-quarters counter-boot kicks
  - **Power Slide (`Shift` or `C` on ground / Gamepad `B` or `LB`)**:
    - High-velocity low-friction slide across diamond-plate steel
    - Drops camera POV to crouch profile (`y = 0.65`) and kicks up lateral spark spray
    - Sliding into opponents trips them, juggling them +18 m/s skyward
  - **Thruster Air-Dash / Evasive Dodge (`Shift` while airborne)**:
    - 22 m/s omnidirectional jet dash with 1.1s cooldown and cyan exhaust plume
  - **Pneumatic Jump (`Space` on ground / Gamepad `A`)**:
    - +15.5 m/s upward thrust with whoosh SFX and dust burst, preserving air-brake shockwave stomp when looking steeply down
  - **HTML5 Gamepad & Controller Engine**:
    - Auto-detection for Xbox, PlayStation, and generic USB/Bluetooth gamepads
    - Analog stick steering & deadzone handling, trigger firing, and haptic actuator dual-rumble feedback
  - **Dynamic HUD Ability Deck**:
    - Sleek bottom HUD badges showing cooldown timers and auto-swapping to controller button glyphs when a gamepad is connected

---

## 🟢 6. Multiplayer, Networking & Match Gating (Completed & Live)
- [x] **Strict Match Gating & Pre-Match Holding Freeze**:
  - The game **NEVER** starts physics, bot AI, or hazard collisions when a player joins via room link (`?room=BF-XXXX`) until the host triggers the launch
  - Player position is rigidly frozen at spawn point `(0, 1.8, isHost ? 22 : -22)` with 0 velocity and 0 drift while `!matchStarted`
  - Opponent AI Bot is strictly disabled in online rooms (`currentTab === 'solo' && matchStarted` only), parking the opponent safely at their spawn
  - Weapon firing, alt-fires, boot kicks, slides, air-dashes, and tether harpoons are blocked while `!matchStarted`
  - Guest start button is locked and disabled with `⏳ WAITING FOR HOST TO START MATCH...`
  - Host start button is locked as `⏳ WAITING FOR OPPONENT TO JOIN...` until `peerConnections.size > 0`
  - When the host clicks `🚀 START MATCH (LAUNCH ALL PILOTS)`, a `start_match_countdown` packet broadcasts to all peers
  - Both players experience a synchronized 3-2-1 countdown sequence with high-tech countdown overlay (`3` -> `2` -> `1` -> `ENGAGE!`), audio beeps, and simultaneous arena drop
- [x] **Bulletstorm Visual & Atmosphere Detailing Overhaul**:
  - **Kinetic Energy Leash (3D Electric Lightning Tether)**: 16-point segmented buffer geometry with dynamic high-frequency electric arc displacement and additive cyan spark emission
  - **3D World-Space Floating Skillshot Badges**: Canvas-rendered billboard badges that spawn at kill coordinates and float skyward +4m with smooth fade
  - **First-Person Weapon Heat Coils**: Glowing radiator heat coils on Shotgun and Railgun barrels that illuminate incandescent orange/red above 40% heat
  - **Visor Impact Splatter**: Dynamic radial screen scratch and splatter overlay triggered on concussive impacts and knockback
  - **Atmospheric Steam Vents & Lava Bubbles**: Continuous white steam bursts from catwalk exhaust pipes and boiling magma bubble embers
- [x] **Multi-Peer Mesh Networking & 2v2 Support**:
  - WebRTC DataChannel mesh connections managed via `peerConnections` Map allowing multi-client connections
  - Dynamic squad roster HUD auto-switching between 1v1 duel display and 4-pilot squad cards (Blue 1 & 2 vs Red 1 & 2)
- [x] **Host Migration Failover**:
  - Seamless failover election promoting the next connected peer to room host if the original host disconnects, preserving active match scores, selected arena map, and destructible cover pillar states
- [x] **Auto-Reconnect & State Recovery (`sync_match`)**:
  - Robust auto-reconnection loop recovering dropped connections without kicking pilots from the room, with instant match state recovery
- [x] **Quick Tactical Pings / Chat Wheel**:
  - Contextual radial ping wheel (`KeyG` or on-screen click) with 4 tactical commands ("ATTACK TURBINE", "WATCH LAVA GEYSER", "REGROUP AT CATWALK", "ENEMY HARPOONED")
  - 3D expanding beacon column with spinning floor rings and network broadcast to all pilots

---

## 🟢 7. Infrastructure & Git Sync (Completed)
- [x] Local Git repository initialized on `main` with feature commits
- [x] Remote GitHub repository linked and active at [`DEADish1/backfire-arena`](https://github.com/DEADish1/backfire-arena)
- [x] All source code, assets, procedural generators, and documentation pushed to `origin/main`
- [x] Production deployed and aliased at [`https://backfire-arena.vercel.app`](https://backfire-arena.vercel.app)
