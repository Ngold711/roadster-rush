# Notes for Claude

Standing rules from the owner for every change to Roadster Rush:

- **Every visual change needs both looks**: a **Classic** version and a **Realistic** version (`SET.real`).
  Each must be placed correctly in its own mode. Classic keeps its flat cartoon style; Realistic gets the extra
  detail (lighting, gloss, shading, glow, soft shadows, wet-road reflections). Screenshot and check both before shipping.
- New scenery and features also need a **Mars** version alongside New York (`onMars()`).
- Show the owner picture mockups before building a new feature or redesign.
- Ship each change as a new build number: update `version.txt`, rebuild `index.html`, and push.

## Classic / Realistic checklist (audited at build 75)

Every in-game element has both versions. When adding something new, add it here too.

| Element | Classic | Realistic |
|---|---|---|
| Sky / skyline (NYC) | cartoon skyline + landmarks | real Manhattan skyline (`bakeManhattan`) |
| Mars backdrop | `bakeMars(g, false)` | `bakeMars(g, true)` |
| Road / sidewalks | flat | gradient asphalt, wet reflections in rain |
| Side buildings (NYC) | `drawBuilding` | `drawBuildingReal` (textured facades, shops, fire escapes) |
| Mars base (habs, domes, solar, Starship) | flat | gloss, glow, seams |
| Street lamps | glow | + wet reflections |
| Traffic cars, Cybertrucks, vans, semis, trailers | flat | `gloss`, `lampGlow`, soft `shadowAt` |
| Campaign billboards | `drawBillboard` | `drawBillboardReal` (steel, catwalk, floodlights) |
| Wanted signs / wall posters | flat | light vignette / wall shading |
| Tunnels (Loop, lava tube) | neon rings | + glow halos, light on road |
| Launch ramp + flip | flat | concrete gradient, floodlights, car sheen |
| Barriers, walls, ramps | flat | gloss, soft shadows, lamp glow |
| Cells, power-ups, rings, letters | flat | glow + glassy highlights |
| Drones, sky rocket | flat | gloss, beacon / exhaust glow |
| People (drivers, Zuck, Optimus) | flat | `volRect` shading, face highlight |
| Meta Quest headsets | flat | glossy shell, logo glow |
| Waymo Way / Optimus Outpost | teal / red theme | lit arch with light cone, glossy signs, billboard wash, shaded graffiti, road light pools |
| Driver seen through rear glass | light tint | darker tint + sheen |

Menus and full-screen UI (start screen, garage, Cyber Crate opening, game over) are shared by both modes on purpose.
