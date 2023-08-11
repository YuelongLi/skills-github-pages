---
title: "Collision Emulator with dynamic frame caching"
date: 2019-05-14
---

In my project, [CollisionEmulator](https://github.com/YuelongLi/CollisionEmulator), I've created a mechanism to emulate collisions between blocks. One of the standout features is the dynamic frame caching mechanism. Let's dive into the equations and algorithms that power this emulator.

### Collision Dynamics: The Math Behind the Movement

When two blocks collide, their post-collision velocities are determined by the conservation of momentum. The equations governing this are:

\[ v1' = v1 + \frac{2m2}{m1 + m2} (v2 - v1) \]
\[ v2' = v2 + \frac{2m1}{m1 + m2} (v1 - v2) \]

Where:
- \( v1' \) and \( v2' \) are the velocities of blocks 1 and 2 after the collision.
- \( v1 \) and \( v2 \) are the velocities of blocks 1 and 2 before the collision.
- \( m1 \) and \( m2 \) are the masses of blocks 1 and 2, respectively.

### Time Management: Ensuring Smooth Transitions

To ensure the simulation runs smoothly, it's crucial to determine the exact time intervals between frames. The `getTimeGap` function calculates the smallest time gap, \( dt \), based on the current velocities and positions of the blocks:

\[ dt = \min \left( \frac{1}{\text{framerate}}, \frac{\text{leftBound of block}}{-\text{velocity of block}} \right) \]

This equation ensures that the time gap is just enough to capture the next significant event, be it a block reaching the left boundary or two blocks colliding.

### Collision Detection: A Continuous Check

The `computeCollisions` function continuously checks for potential collisions. The time gap until the next collision, \( \text{timeGap} \), between two blocks, a and b, is given by:

\[ \text{timeGap} = \frac{\text{leftBound of a} - \text{rightBound of b}}{v_b - v_a} \]

Where \( v_a \) and \( v_b \) are the velocities of blocks a and b, respectively.

### Dynamic Frame Caching: The Heart of the Emulator

The `getFrame` function is pivotal in ensuring a seamless simulation experience. It uses the above equations to dynamically compute and cache the positions of all blocks at a specified timestamp. This dynamic approach, combined with the meticulous collision handling, results in a smooth and accurate simulation.

### Conclusion

The CollisionEmulator is a testament to the intricate blend of physics and coding. The underlying equations and algorithms ensure its accuracy and efficiency. As I venture into the professional world, this project stands as a beacon of my dedication, proficiency, and passion for problem-solving and innovation.
