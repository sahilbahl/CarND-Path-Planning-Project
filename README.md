# Path Plannning Project
**Aim**:
In this project, your goal is to design a path planner that is able to create smooth, safe paths for the car to follow along a 3 lane highway with traffic. A successful path planner will be able to keep inside its lane, avoid hitting other cars, and pass slower moving traffic all by using localization, sensor fusion, and map data.

**Implementation**:
The project focuses on 3 goals .Below I explain the strategy used to tackle the three points.
  - **Path Generation**
        Here I followed the approach explianed in the project walkthrough.
        I ended up using the same technique of using some previous path points along with some generated points which are created by applying a spline to distant waypoints.
  - **Collision Avaoidance**
    I started off using the same strategy mentioned in the walk through of slowing down when getting an obstacle ahead. I modified the factor by which the car deacclearates and also played with the threshold distance to get a optimal result.
  - **Time**
    Here I choose a strategy to always travel in the lane where the vehicle closest to my vehicle is the farthest. Whenever the car sees a lane with a vehicle farther than in the current vehicle it makes a lane switch.
However here to prevent frequest switches and avoid accidents while switching lanes I have applied few conditions.
    - Switch only if the lane with the farthest next vehicle is atleast 40 displacement away from your current lane next vehicle. (This is to avoid switching lane without too much gain )
    - If we need to switch from Lane 0 to Lane 2 it is important to check if lane 1 is not having a vehicle nearby. I only make a switch to the next lane if the next vehicle in the next lane is atleast 40 displacement away.

# Further Improvements
  - Based on consecutive mesurements compare the speeds of the near by vehicles to modify vehicle's speed.
  - Apply a more robust State Machine as well as some probabilisitc model.
