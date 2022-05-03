# Aim Lab
Kawin Tiyawattanaroj and Mikako Inaba

[Online Demo](https://kawint.github.io/COS426_Final_Project/)


## Building the Project for the Web
Once you are happy with your project, try building a production bundle using `npm run build`. This will place an optimized and minified executable version of your project in the `./build/` directory. Test out this production build by setting `./build/` as your working directory and starting out a python server.

Once you have a working production build and are ready for the site to go live, you can deploy your project straight to GitHub Pages via `npm run deploy`. Note that this requires that (1) your project is part of a repository, and (2) you have correctly set up your project's `package.json` file.

## Abstract
The goal of this project was to create a first person shooter (fps) game to allow players to practice aiming and learn to navigate scenes using commonly used controls. The game tracks precision, accuracy, and time, different measures of performance. The objective of the game is to maximize precision and accuracy while also minimizing time. As in many fps games, players can move through the scene using WASD keys and look using the mouse. The targets generate in random locations to allow players to get comfortable with these controls.

## Introduction


## Methodology
### Rendering the Scene and Lighting

### Player Movement 

### Generating Targets and Collision Detection 
All the targets in the game were generated using the three.js SphereGeometry as the geometry and the three.js MeshPhongMaterial as the material. Each round consists of five different targets – one big target and four smaller targets. The big target has a radius four times that of the smaller targets. At the beginning of each round, the first of the five targets is generated at a random position within the scene. The first target is always the big target. When this target is shot, the four smaller targets are generated about the center of the original target. Once all the smaller targets are hit, the round ends. 

To detect collisions, the three.js Raycaster was used with the normalized coordinates of the mouse and the camera as the origin of the ray. When a collision was detected, the click was accompanied with a sound. The distance between the camera and the intersection calculated by the Raycaster was used in measuring precision. 

### Tracking Statistics
To track the precision, the score was incremented depending on how close the click was to the center of the target. The maximum score per target was set such that the maximum score attainable across all the rounds in the game was 100. If the click was within half the radius of the target, the score was incremented by the maximum score. Otherwise, the player received only half of the maximum score.

To calculate whether the click was within half the radius of the target, some vector algebra was performed. The angle between the vector from the center of the target to the camera and the vector from the center of the target to the intersection (calculated via the Raycaster as previously described) was found. This angle was used to determine how the score should be updated. 

The accuracy was measured as the ratio of the number of clicks that hit a target to the number of total clicks made by the player. To help players improve precision and accuracy, the cursor was replaced with a crosshair. As another measure of performance, the total time per game was also tracked. Both the score (our measure of precision) and the accuracy is displayed during game play, and all three measures of performance are displayed at the end of all the rounds.
 
## Results 
The main goal of our project was to create a game to help players improve their aim and practice navigating scenes using controls commonly used in fps games. Therefore, we measured success by having our peers play the game. Tracking precision and time and replacing the cursor with a crosshair are examples of features that we added in response to feedback. Additionally, Mikako did not have any experience with fps games and initially had difficulty navigating the scene. However, she became significantly better at moving to find targets throughout the course of building the game.

We also measured success with respect to completion of the MVP and stretch goals we initially proposed. We completed all of our MVP features: generating random targets, detecting collisions, tracking score, and rendering the scene and lighting. We were able to get started on our stretch goals, including tracking accuracy, precision, and time, adding some obstacles, and splitting a big target into smaller targets. We also added other features such as the sound effect when a target is hit and the crosshair to help players aim better as well as accepting player input to choose the number of rounds and replay the game.

Overall, measured by peer feedback and completion of our MVP and stretch goals, we were able to fulfill our initial goal.

## Discussion and Conclusion

## Contributions
Kawin focused on rendering the scene and lighting and player movement, while Mikako mainly worked on generating the targets and collision detection and tracking statistics. 

## Works Cited

## License
[MIT](./LICENSE)
