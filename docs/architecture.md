# Architecture overview

## Runtime

The authoritative server owns table state, validates actions, advances phases, and broadcasts a client-safe view. Clients render that view and submit player intent rather than mutating shared state directly. Bots use the same action boundaries as human players.

## Rules and tests

Poker evaluation, betting behavior, perks, bankroll carry-over, and match scoring are separated from rendering. Headless tests exercise the rules, while network smoke tests launch a server and multiple automated clients.

## Development observability

Debug-only hooks expose table state, deterministic screenshots, camera controls, and scripted actions. These make visual comparisons and regression checks repeatable without shipping the tooling in production builds.

## Asset pipeline

Characters move through versioned references, generated source meshes, measured review renders, authored low-poly kits, and explicit shipping scripts. Approved references and release artifacts are never overwritten.

