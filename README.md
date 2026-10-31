# Anzu Hanashiro: The Moonlit Kingdom

<div align="center">

![Three.js](https://img.shields.io/badge/Engine-Three.js-black?logo=three.js)
![Language](https://img.shields.io/badge/Language-JavaScript_ES2022-F7DF1E?logo=javascript&logoColor=black)
![Rendering](https://img.shields.io/badge/Rendering-WebGL-990000?logo=webgl)
![Platform](https://img.shields.io/badge/Platform-Browser-blue)
![License](https://img.shields.io/badge/License-Original_Project-green)

**A playable, third-person 3D open-world browser game built with native ES modules and Three.js.**

Explore a living fantasy kingdom, cross a river into guarded castle grounds, wander through an elven forest, and approach the white dragon at the mountain frontier.

</div>

---

## Overview

**Anzu Hanashiro: The Moonlit Kingdom** is a complete browser-based 3D game prototype focused on exploration, atmosphere, NPC interaction, and a flexible graphical settings system.

The project uses a real WebGL scene rather than a 2D canvas illusion:

- Perspective 3D camera
- 3D terrain geometry
- Directional sun and hemisphere lighting
- Soft shadow maps
- ACES tone mapping
- Physical water material
- Procedural grass instancing
- Animated NPCs and world actors
- Distance fog and day/night transitions
- A responsive HUD and minimap
- Persistent in-browser settings

> This project is an original browser game experience. It is not intended to replicate an unreleased commercial engine or claim production parity with AAA titles such as GTA V.

---

## Key Features

### Open World

- Large connected 3D world
- Verdant town with 30 furnished house structures
- Stone road and detailed bridge system
- Reflective river and flowing visual treatment
- Moonlit castle with towers, banners, windows, and fortified entry
- Dense tree forest
- Elven homes and five elven characters
- Snow-capped mountain region
- Large sleeping white dragon encounter
- Town NPC population with wandering movement
- Bob the cat interactable at the village
- Roof birds and animated world actors

### Character and Camera

- Playable Anzu Hanashiro character group
- Third-person chase camera
- Mouse-look with pointer-lock support
- Walking, sprinting, crouching, lying-down, and jump-ready animation states
- Configurable camera sensitivity
- Camera-relative movement
- World-bounded player movement

### World Systems

- Day/night transition controls
- Sunny and rainy world states
- Dynamic location labels
- Circular minimap
- Fixed or rotating minimap support
- Compass direction
- In-game clock
- World map overlay
- NPC dialogue system
- House and dragon interactions

### Settings and Configuration

- Video and world-performance settings
- Graphics presets and FPS targets
- Dynamic renderer pixel scaling
- Shadow quality
- Anti-aliasing toggle
- Bloom, motion blur, and chromatic toggles
- Volume sliders
- Camera sensitivity
- Y/X-axis inversion options
- Minimap, compass, subtitle, and dialogue options
- Key rebinding interface
- `localStorage` persistence
- Apply, Cancel, and Reset lifecycle
- Experimental reality shaders
- Gravity-based “Break Settings” mode and “Fix Menu” restoration

---

## Screenshots

Launch the game and press `F11` for fullscreen presentation.

Recommended capture views:

1. Verdant Town entrance
2. Castle and tower approach
3. River bridge
4. Elven forest
5. Mountain dragon overlook
6. Settings menu
7. Night and rain conditions

---

## Quick Start

### Requirements

- A modern desktop browser
- WebGL 2 support
- Hardware acceleration enabled
- A local HTTP server

### Recommended launch

Run from the project directory:

```powershell
python -m http.server 4173
```

Then open:

**http://127.0.0.1:4173/**

ES modules should be served over HTTP rather than opened directly through `file://`.

### Alternative launch

Using Node.js:

```bash
npx serve .
```

Or use VS Code Live Server and open the workspace root.

---

## Controls

| Action | Default |
|---|---|
| Move forward | `W` |
| Move backward | `S` |
| Move left | `A` |
| Move right | `D` |
| Sprint | `Shift` |
| Jump | `Space` |
| Interact | `E` |
| Crouch | `C` |
| Lie down | `X` |
| World map | `Tab` |
| Mouse look | Pointer lock after clicking the game |
| Weather | On-screen button |
| Time of day | On-screen button |
| Settings | `⚙ Settings` button |

Additional key bindings can be assigned from the Settings → Controls panel.

---

## In-Game Interactions

Move close to an actor and press `E`:

| Target | Interaction |
|---|---|
| Bob the Cat | Displays “Hello, darling!” |
| Town NPC | Displays name and NPC role |
| Castle resident | Displays royal dialogue |
| Castle guard | Displays guard dialogue |
| Elven character | Displays an elf-specific greeting |
| Bartender | Displays tavern dialogue |
| Town house | Displays house encounter information |
| White dragon | Displays the dragon petting interaction |

---

## Settings Menu

Open the settings panel using the `Settings` button in the bottom-right HUD.

### Graphics and Frame Rates

- Low, Medium, High, and Ultra presets
- 30, 60, 120 FPS, or uncapped targets
- Dynamic resolution scaling
- Shadow quality
- Particle limit
- Anti-aliasing
- Bloom
- Motion blur
- Chromatic aberration

### World Performance

- Render distance levels
- NPC density levels
- Resolution modes
- Texture and graphics presets
- Fog distance adjustment

### Audio

- Master
- Music
- Sound effects
- Dialogue
- Ambient environment

### Controls and HUD

- Camera and aiming sensitivity
- Invert X/Y
- Custom keyboard bindings
- Rotating or fixed minimap
- Compass visibility
- Subtitles
- Dialogue readability backing

Settings are saved using browser `localStorage`.

---

## Project Structure

```text
.
├── index.html          # Semantic game and settings interface
├── styles.css          # Responsive HUD, overlays, settings, visual effects
├── game.js             # Three.js world, systems, renderer, and UI logic
├── three.module.js     # Local Three.js ES module
└── README.md           # Project documentation
```

---

## Technical Architecture

### Rendering Pipeline

- `THREE.WebGLRenderer`
- Perspective projection camera
- Shadow mapping
- Color-space conversion
- ACES filmic tone mapping
- Fog-based world depth
- Real-time 3D scene graph
- Instanced grass meshes
- Mesh-standard and physical materials

### Scene Composition

The world is assembled from modular scene construction functions:

- Terrain generation
- Road and bridge creation
- Castle construction
- House batching
- Tree generation
- Elven settlement creation
- Character models
- NPC population
- Cat actor
- Pigeon actors
- Snow mountain placement
- Dragon encounter

### Input

The input system listens for keyboard and pointer-lock mouse events. Movement is normalized and transformed through the camera yaw for consistent directional control.

### Settings Lifecycle

```text
Stored Settings
      │
      ▼
localStorage Load
      │
      ▼
Merged with Defaults
      │
      ▼
Draft Settings ── Preview changes
      │
      ├── Apply ──► Persistent state + renderer update
      ├── Cancel ─► Restore applied state
      └── Reset ──► Restore safe defaults
```

---

## Performance Notes

Recommended browser settings:

- Enable hardware acceleration
- Close unused GPU-intensive tabs
- Use High rather than Ultra on integrated graphics
- Lower resolution scaling for weak devices
- Use the 60 FPS target
- Disable the shadow map on very low-end hardware

The project uses local source files and has no required network runtime dependencies.

---

## Browser Compatibility

Best experience:

- Microsoft Edge
- Google Chrome
- Mozilla Firefox
- Chromium-based browsers

Required browser capabilities:

- ES2022 JavaScript
- ES modules
- WebGL
- Pointer Lock API
- Local Storage
- `requestAnimationFrame`

---

## Controls and Accessibility

- Pointer-lock mouse look can be exited with `Esc`
- Settings menu remains keyboard-operable
- HUD location, compass, clock, and weather are text-readable
- Dialogue interface includes a named speaker and message
- Key rebinding is available
- Minimap and compass visibility can be controlled
- Reduced-motion or visual-distortion options are isolated to the experimental settings group

---

## Troubleshooting

### The game page is blank

- Confirm that it is running through HTTP
- Refresh the browser after starting the server
- Check that `three.module.js` is present next to `game.js`
- Confirm hardware acceleration is enabled

### Pointer lock does not activate

Click inside the game canvas. Press `Esc` to release the mouse.

### WebGL errors appear

- Update the browser and graphics driver
- Disable browser-level WebGL blocking extensions
- Try a Chromium browser
- Lower graphics settings

### Settings do not appear saved

Use the `Apply Changes` button. Browser privacy extensions may block `localStorage`.

### Module-loading error

Do not open the HTML by double-clicking it. Use an HTTP server:

```bash
python -m http.server 4173
```

---

## Known Limitations

This is a playable browser world, not a full AAA game production:

- Geometry is built from procedurally composed primitives
- Character meshes are stylized rather than photorealistic assets
- Town houses share modular construction patterns
- Castle interiors are represented through the world interaction layer
- NPCs currently use shared procedural models
- Audio settings are represented in the UI but may require added production audio assets
- Collisions and interiors can be expanded with navigation meshes and collision geometry
- The dynamic FPS selector should be connected to an accumulator in the final engine build

---

## Production Roadmap

### Phase 1 — Content

- Replace primitive meshes with modeled and textured assets
- Add baked house interiors
- Add castle rooms and climbable tower stairs
- Add pubs, workshops, markets, and gardens

### Phase 2 — Gameplay

- Navigation meshes and advanced NPC routines
- Interactive quest states
- Inventory and mounts
- Weather particles and seasonal changes
- Save checkpoints and world persistence

### Phase 3 — Rendering

- HDR environment maps
- GPU-driven grass rendering
- Cascaded shadow maps
- SSAO
- Temporal anti-aliasing
- Screen-space reflections
- Deferred material pipeline
- Post-processing composer

### Phase 4 — Performance

- Streaming world chunks
- Frustum and occlusion culling
- Instanced LODs
- GPU skinning
- Asset and texture compression
- Worker-based AI scheduling
- Automated graphics presets

---

## Development

The project intentionally avoids a framework dependency for core logic.

Core source is split into:

```text
HTML: structure, HUD, settings interface, dialogue
CSS: themes, layout, responsive behavior, visual states
JavaScript: game systems, scene generation, settings state, interaction
Three.js: WebGL rendering primitives and scene graph
```

To modify the world, inspect and extend the constructors inside `game.js`:

- `createWorld()`
- `createTown()`
- `createHouse()`
- `createForest()`
- `createCastle()`
- `createNPCs()`
- `createPlayer()`
- `createDragon()`
- `createBob()`

---

## Credits

**Concept:** Anzu Hanashiro: The Moonlit Kingdom  
**Rendering:** Three.js WebGL  
**Implementation:** Native HTML5, CSS3, ES modules, and JavaScript  
**Game world:** Procedural primitives, original scene composition, and local runtime assets

---

## License

Unless project-specific licensing is added, this repository should be treated as original proprietary work for demonstration and development purposes. Three.js remains subject to its own MIT license.

---

<div align="center">

**Enter Verdant Town. Find the bridge. Climb toward the castle. Meet the dragon beyond the snow.**

</div>
