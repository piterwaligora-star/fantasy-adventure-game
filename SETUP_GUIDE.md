# Fantasy Adventure Game - Setup Guide

## Quick Start

### Step 1: Create Project Structure in Unity

1. Open Unity Hub and create a new project with Unity 2021.3 LTS
2. Name it `fantasy-adventure-game`
3. Choose 3D template

### Step 2: Set Up Folders

Create these folders in `Assets/`:
```
Assets/
├── Scenes/
├── Scripts/
│   ├── Player/
│   ├── Enemy/
│   ├── World/
│   ├── UI/
│   └── GameManager.cs
├── Prefabs/
├── Models/
└── Materials/
```

### Step 3: Clone the Repository

```bash
git clone https://github.com/piterwaligora-star/fantasy-adventure-game.git
cd fantasy-adventure-game
```

Copy the Scripts folder into your Unity project's `Assets/` folder.

### Step 4: Create the Main Scene

1. Create a new scene: `Assets/Scenes/MainGame.unity`
2. Save it

### Step 5: Create Player

1. Create an empty GameObject and name it "Player"
2. Add components:
   - Add `Rigidbody` component
   - Set Mass to 1
   - Freeze Rotation X, Y, Z
   - Add `Capsule Collider` component
   - Add `PlayerController` script
   - Add `PlayerHealth` script
   - Add `PlayerAttack` script
   - Tag it as "Player"

3. Create a child object "CameraHolder":
   - Add `Camera` component
   - Position at (0, 0.6, 0)

4. Create a child object "Sword":
   - Add a cube model
   - Scale to (0.2, 0.1, 1)
   - Position at (0.3, -0.3, 0.5)

### Step 6: Create Enemy

1. Create an empty GameObject and name it "Enemy"
2. Add components:
   - Add a cube model as child (for visuals)
   - Add `Rigidbody` component
   - Add `Capsule Collider` component
   - Add `Nav Mesh Agent` component
   - Add `EnemyHealth` script
   - Add `EnemyAI` script

3. Create a Canvas child object for health bar:
   - Add `Image` component (red background)
   - Create child Image for health fill (green)
   - Assign to EnemyHealth script

### Step 7: Create World Objects

#### Treasure Chest:
1. Create a cube and name it "Chest"
2. Add components:
   - `Box Collider` (check "Is Trigger")
   - `Chest` script

#### NPC:
1. Create a capsule and name it "NPC"
2. Add components:
   - `Capsule Collider`
   - `NPC` script

### Step 8: Create UI Canvas

1. Create a Canvas (UI > Canvas)
2. Add UI elements:

**Health Bar Panel:**
- Panel named "HealthBar"
- Add Image (red background)
- Add child Image for fill amount (green)
- Add Text showing "Health: 100/100"

**HUD Panel:**
- Panel with Text for Gold: 0
- Panel with Text for Enemies: 0

### Step 9: Build the Scene

1. Add an empty GameObject "GameManager"
2. Add `GameManager` script component
3. Add some lighting (Directional Light)
4. Add terrain or ground plane

### Step 10: Configure Tags

Go to Edit > Project Settings > Tags and add:
- `Player`
- `Enemy`
- `Chest`

### Step 11: Configure Layers

Set up Ground layer for player movement detection.

### Step 12: Test the Game

1. Press Play in Unity Editor
2. Use WASD to move
3. Mouse to look around
4. Space to jump
5. Left Click to attack
6. E to interact with chests/NPCs

## Troubleshooting

### Player falls through ground
- Make sure the ground has a `Collider` component
- Check Ground Layer is set in PlayerController

### Enemies don't move
- Make sure you have NavMesh baked in the scene
- Window > AI > Navigation > Bake

### Health bar doesn't appear
- Assign the Image component in the Inspector
- Make sure canvas is set to "World Space"

### Player can't interact with objects
- Check objects have Collider components
- Make sure they have IInteractable implementations

## Next Steps

- Add animations for player and enemies
- Create more levels/scenes
- Add sound effects
- Improve UI/UX
- Add more enemy types
- Create a complete quest system
- Add power-ups and loot system

---

Happy developing! 🎮✨
