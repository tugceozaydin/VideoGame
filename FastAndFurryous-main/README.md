# Fast and Furryous

## Milestone 4: Final Game

### Playability
- Tutorial level
  - File: `src/cpp/world_system.cpp`
  - Function: `WorldSystem::tutorial_level()`
  - Relavant Line Numbers: `515 - 525`

- Implemented different weapons
  - File: `src/cpp/shooting_system.cpp`
  - Function: `ShootingSystem::shoot()`
  - Relavant Line Numbers: `111 - 149`

- Crosshair angle indicators:
  - File: `src/cpp/world_init.cpp`
  - Function: `createCrosshair()`
  - Relavant Line Numbers: `450 - 494`

### Robustness
The game was profiled using [Tracy](https://github.com/wolfpld/tracy#tracy-profiler), and optimization was done in multiple bottleneck locations.
The following functions were optimized for better performance and memory management:
- `RenderSystem::drawText()` in `src/cpp/render_system.cpp`
- `GameController::step()` in `src/cpp/game_controller.cpp`
- `RenderSystem::transform()` in `src/cpp/render_system.cpp`
- `createText()` in `src/cpp/world_init.cpp`
- `TextManager::getGlyphs()`, `TextManager::getItalicGlyphs()`, and `TextManager::getBoldGlyphs()` in `src/hpp/text_manager.hpp`

### Stability
- Consistent resolution
  - File: `src/cpp/common.cpp`
  - Function: `scaleToScreenResolution()`
  - Relavant Line Numbers: `88 - 92`
    
### Creative Component
- Added particle system with instanced rendering
  - File: `src/cpp/particle_system.cpp`
  - Function: `step()`
  - Relavant Line Numbers: `64 - 90`

- Added bouncing physics
  - File: `src/cpp/character_grounded_state.cpp`
  - Function: `handleGrenadeBounce()`
  - Relavant Line Numbers: `516 - 550`

- Added Explosion with effects
  - File: `src/cpp/world_init.cpp`
  - Function: `createExplosion()`
  - Relavant Line Numbers: `592 - 624`

- Camera that is controlled with mouse input
  - File: `src/cpp/game_controller.cpp`
  - Function: `GameController::moveCamera()`
  - Relavant Line Numbers: `148 - 170`

- Parallax scrolling backgrounds
  - File: `src/cpp/map.cpp`
  - Function: `MapSystem::Map::build()`
  - Relavant Line Numbers: `65 - 181`

- Characters sprites are faded when not selected
  - File: `src/cpp/render_system.cpp`
  - Function: `RenderSystem::animateSprite()`
  - Relavant Line Numbers: `169 - 174, 204`

## Player Feedback changes
Our team has made numerous changes based on feedback we have received from xplay sessions as well as play testing from non CPSC427 related parties. 
- One of our biggest issue has always been stability. Since the last milestone, stability of our overall game has proved immensly. 
- In addition, we noticed from both the xplay session as well as outside play testing that our control scheme was too convoluted. To address this we reduced the amount of keys required to play our game and consolidated several controls to the mouse such that controls are much more intuitive.
- Regarding gameplay, the most common feedback we received was that movement and character switching was almost completely pointless. Instead of allowing players to choose which character to move with, we instead restrict the player's selected character to promote strategy and forward thinking

