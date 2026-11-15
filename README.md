# 🔥 BACKFIRE

> **Browser 3D Recoil-Combat Arena — Zero Damage Weapons, Pure Kinetic Lethality.**

Live at: **[https://backfire-arena.vercel.app](https://backfire-arena.vercel.app)**

---

## 🎮 Concept & Rules

In **BACKFIRE**, your weapons deal **zero direct health damage**. Instead, projectile reaction forces propel you across the arena at blistering speeds. Kills are earned exclusively through **environmental pulverization** — slamming your opponents into lethal hazards:
- ⚡ **Spike Walls** (North & South perimeters)
- 🌀 **Rotary Turbine** (West bulkhead — high-speed shredder)
- 🌋 **Molten Pit** (Arena center — instant vaporization)

---

## 🛠️ Kinetic Weapon Arsenal

| # | Weapon | Recoil Impulse | Concussive Force | Spread | Style |
|---|--------|----------------|------------------|--------|-------|
| **1** | **Breaker 12G** | High (27.0) | Heavy (40.0) | 8 Pellets | Close-range blast propulsion & wall checks |
| **2** | **Jackhammer** | Continuous (3.9) | Rapid (11.0) | Tight | Fully-automatic recoil jet flight |
| **3** | **Rail Slugger** | Extreme (23.0) | Massive (70.0) | Pinpoint | Long-range concussive sniper & air juggles |

### 🪝 Kinetic Harpoon (Right-Click)
Latch onto arena walls, pillars, or directly onto the enemy pilot to whip around corners, sling into jump pads, or pull targets directly into hazard blades.

---

## 🕹️ Controls

- **`WASD`** — Fine drift thrusters & vector steering
- **`Left-Click`** — Fire weapon (propels pilot in opposite direction)
- **`Right-Click`** — Launch Kinetic Harpoon / Tether
- **`1`, `2`, `3` or `Scroll Wheel`** — Switch active weapon
- **`Spacebar`** — Inertial air-brake / stabilize velocity
- **`Look Down + Shoot`** — Rocket Jump / Flight boost
- **`Esc`** — Release cursor lock / Open match lobby

---

## 🌐 Architecture & Networking

- **Engine**: Three.js (r128 WebGL renderer)
- **Audio**: Procedural Web Audio API synthesizer (no external audio assets required)
- **Multiplayer**: Peer-to-peer WebRTC DataChannels using PeerJS with public STUN signaling
- **Hosting**: Vercel static edge distribution
- **Room System**: URL-encoded instant room codes (`?room=BF-XXXX`)

---

## 🚀 Running Locally

```bash
# Clone the repository
git clone git@github.com:DEADish1/backfire-arena.git
cd backfire-arena

# Serve statically with any HTTP server
npx serve .
# or
python3 -m http.server 8080
```
