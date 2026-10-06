# TickTap VR — Meta Quest Hand-Tracked Puzzle Game

## Competition
- **Meta VR Start Developer Competition 2026**
- Submission deadline: **November 18, 2026**
- Track: **Gaming** — "Games designed for hands-first input"
- Devpost: https://start-developer-competition-26.devpost.com/

## Core Concept
Port of TickTap mobile (ticktap.gg) adapted for spatial VR:
- **Mechanic**: Time moves when your hand moves. Hand still = time frozen.
- **Goal**: Guide an object through spatial obstacles to reach the target zone before time runs out.
- **Input**: Hand tracking only (controller support optional). Seated, stationary play.
- **Sessions**: Under 10 minutes. Fast cold start, clean pause/resume.

## Design Transformation (2D → VR)
| Mobile (TickTap) | VR (TickTap VR) |
|---|---|
| Drag finger on screen | Move hand in space |
| 2D lanes, top-down scroll | 3D corridor/tunnel, objects fly toward you |
| Obstacles cross lanes | 3D obstacles move through space |
| Stars to collect | Spatial pickups (gems/orbs) |
| Timer bar on screen | Spatial timer (ring closing, or ambient cue) |
| Portrait phone screen | Forward-facing seated view |

Key principle: **identical game feel, spatial presentation**. The "time moves when you move" mechanic translates directly — hand velocity controls time flow.

## Target Platforms
- **Meta Quest 3 / 3S** (primary, testable now)
- **Meta VR Glasses** (ships spring 2027, use Meta XR Simulator for dev)
- Same OS — build once, runs on both

## Tech Stack
- **Platform**: Native Android (Meta XR SDK) — simplest path from macOS
- **CLI**: `metavr init` for project bootstrap
- **SDKs**: Meta XR SDK (hand tracking, passthrough, spatial anchors)
- **Assets**: Meta Asset Library (1.5M free 3D assets) for rapid prototyping
- **Agentic tools**: https://github.com/meta-quest/agentic-tools
- **Simulator**: Meta XR Simulator (for VR Glasses testing without hardware)

## Visual Style
- Minimalist, clean geometry — matches TickTap mobile aesthetic
- Dark background with bright accent objects
- No textures needed — solid colors, glow effects, simple shapes
- Passthrough-compatible (mixed reality option)

## Code Philosophy
- Comments in English, only when explaining WHY
- Keep it simple — tight vertical slice > broad prototype
- Iterate fast, polish what matters
- JSON configs for level data (carry over from mobile where possible)

## Project Structure
```
CLAUDE.md          # This file
README.md          # Public-facing overview
app/               # Android app source
  src/
  build.gradle
levels/            # Level configs (JSON)
assets/            # 3D models, materials, sounds
shaders/           # Shader files
docs/              # Design docs, specs
  game-design.md   # Detailed game design document
  tech-stack.md    # SDK setup, build instructions
```

## Reference
- **Mobile game repo**: TickTap (Godot 4.5, iOS/Android)
- **Mobile game design**: See ticktap repo's CLAUDE.md for full mechanics, level design, obstacle types
- **Competition blog**: https://developers.meta.com/blog/meta-connect-2026-vr-start-developer-competition/
- **Meta XR SDK docs**: https://developers.meta.com/horizon/develop
- **Hand tracking guide**: https://developers.meta.com/horizon/documentation/unity/unity-handtracking/

## Milestones
1. **Week 1-2**: SDK setup, hand tracking prototype, time-moves-when-you-move mechanic working
2. **Week 3-4**: Core gameplay loop — obstacles, scoring, one complete level
3. **Week 5**: Polish — visuals, sound, haptics, juice
4. **Week 6**: Testing, bug fixes, submission prep, Devpost page
