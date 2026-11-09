# LUMINA project context

## Product

LUMINA is a Diwali-themed ECE campus competition. Participants work in teams of three. The experience combines role-based multiplayer, ECE puzzles, LED challenges, and a browser circuit lab. The intended event size discussed so far is approximately 5–15 teams.

The product name is **LUMINA**. Do not brand it as “Lumina ’26”; the event can be identified as the Diwali edition where useful.

## Intended technology direction

The current prototype is plain HTML, CSS, and JavaScript. The earlier target deployment plan mentioned Vercel for static frontend hosting and Firebase Realtime Database for real-time state. The backend is not implemented or finalized. Confirm architecture decisions before replacing the current approach.

All current game data and demo scores are stored in browser localStorage. This is only for a one-browser prototype.

## Pages currently in the repository

- `index.html` / `lumina-registration.html`: team registration entry
- `lumina-home.html`: signed-in team dashboard, event timeline, roster
- `lumina-leaderboard.html`: demo leaderboard
- `lumina-pataki-clash.html`: Round 1 role entry
- `lumina-pataki-crafter.html`: Bomb Maker station
- `lumina-pataki-thrower.html`: Thrower station
- `lumina-pataki-builder.html`: Builder station
- `lumina-vault.html`: Round 2, four-stage circuit code vault
- `lumina-rangoli.html`: Round 3, timed eight-LED pattern challenge
- `lumina-final-boss.html`: Round 4, drag-and-wire circuit simulator
- `lumina-pataki-role.js` and `lumina-pataki-role.css`: shared Round 1 station behavior and styles

These are prototypes, not production-ready implementations.

## Round requirements

### Round 1 — Pataki Clash

Three separate stations:

- **Bomb Maker:** solve short ECE puzzles to add ammo to the team supply. Keep ammo scarce.
- **Thrower:** at most three shots per match. The player calculates launch angle from the displayed range equation. Only precise shots interrupt the rival build. Do not write to the database while the angle control is moving.
- **Builder:** complete four construction stages and advance team build progress. Do not use Builder HP or repair-HP mechanics.

Only one player should have each role. This is a required future backend rule; the current role entry is a demo selector and does not enforce identity.

### Round 2 — Crack the Circuit Code

A timed four-level vault: logic gates, resistor color bands, circuit fault detection, and binary conversion. Keep answer validation authoritative on the server when a backend is added.

### Round 3 — The Rangoli Breadboard

Eight LEDs arranged in a rangoli/diya pattern. The player infers which LED comes next from a clue and lights the sequence under time pressure. Wrong picks cost time. The current sequence set and scoring are demo content and can be revised.

### Round 4 — The Final Boss

A free-build virtual breadboard with modules and components. The target is a four-LED sequential Diya chaser using an Arduino-style microcontroller module. The player may build freely, but the circuit checker must validate the target connectivity. Current behavior checks a simplified graph and animates a simulated result; it is not a SPICE/electrical solver and is not connected to real hardware.

## Data and security boundaries

- Separate URLs or hidden controls do not prevent access. Enforce team membership, room membership, and unique role assignment in trusted backend rules/functions.
- Clients should submit actions; authoritative logic should validate ammo, shot count, angle/hit window, build progress, match timer, and scores.
- Scope real-time listeners to a team or room. Do not broadcast all teams' private player data.
- Do not store plaintext secrets or trust browser localStorage for one-time registration or scoring.
- Keep round data compact and event-based; the Thrower's aim slider should remain local until a shot is submitted.

## Current known limitations

The prototype has no shared backend, cross-device sign-in, trusted role assignment, durable team registration, server-side scoring, or production circuit simulation. The seeded leaderboard rows are sample preview data. Treat these as known limitations, not completed requirements.