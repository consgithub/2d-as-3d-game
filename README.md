# 2D game with illusion of 3D

A 2D pygame project that creates a pseudo-3D environment using raycasting algorithms

## How it works

**Movement**:
- Uses angle of direction of player and speed of movement to calculate dx and dy by which the player's co-ordinates need to be changed 
- Uses dx and dy increments to check for collisions 
**Raycasting:**
- Calculates x value of distance of first intersection from player using the depth of the vertical (diagonal) and y vertical distance
- Calculates further points of intersection by obtaining dy and delta depth using dx = 1 
- And same process but switched for horizontal lines on grid
- Smaller depth between vertical and horizontal used as actual depth (this is first wall)
**3D Projection:**
- Projection of objects on screen in 3D form calculated by using half of the resolution width divided by tan of half of the FOV (FOV=pi/3) to obtain screen distance (distance between player and screen)
- Projection height of walls calculated by using similar triangles: projected height / screen distance calculated has the same ratio as wall height / depth
- Wall height = 1 so projected height = screen distance / depth 
- Value of depth of ray determines colour to add lighting
- Convex walls fishbowl effect due to use of cartesian coordinate system along with polar fixed by multiplying depth value by cos of angle of players direction subtracted by ray angle
**Other:**
- Number of rays less than screen resolution in width to maintain better performance

## Controls

- **WASD**: Movement
- **Arrow Keys (Left/Right)**: Look around

## Installation

1. Clone the repository
2. Install pygame:
   ```bash
   pip install pygame
   ```

## How to Run

```bash
python main.py
```