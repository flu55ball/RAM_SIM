# 03 RAMSIM 2 beta development

After the pre-alpha stage, the project was rebuilt and refocused as **RAMSim 2.0**. This version moved away from the original spatial-audio-led idea and focused more directly on creating a working VR RAM puzzle.

## Initial setup

* The project was set up in **Unity version 2022.3.62f3**.
* The basic Unity project setup was completed first.
* The **Pico SDK** was installed so the project could be developed for the Pico headset.
* This version of the project was treated as a cleaner setup after the earlier spatial audio demo issues.
* The aim was to create a more stable project that focused on the core RAM interaction.

## 3D model sourcing

* I then went about sourcing the 3D models that I needed.
* The motherboard model was found on **BlenderKit** in Blender.
* The bedroom 3D model was also found on **BlenderKit**.
* These models were imported using **USD**.
* The materials came in very simply, which made the import process easier.
* The models generally did not need too much fixing.

## Motherboard model fixes

* Some of the verts on the motherboard components needed to be fixed.
* I also had to fix all the normals.
* This led to having to re-import the motherboard at one stage with the fixed normals.
* I modified the motherboard slightly so it would line up with the four RAM slots needed for the game.
* Originally, the motherboard had eight RAM slots.
* The final game only needed four RAM slots, so the model was adjusted to better fit the puzzle design.

## Bedroom model setup

* The bedroom model was used as the main environment for the game.
* This gave the RAM puzzle a more complete scene to exist inside.
* The bedroom model was imported using the same general USD workflow.
* The simple material import helped keep the setup manageable.

## RAM stick setup

* The RAM sticks were set up as the main interactive objects in the game.
* I had to custom make the labels for all the RAM sticks using ChatGPT.
* The RAM sticks were colour-coded so they could be identified more easily.
* The colour coding also helped support the puzzle logic, especially where one stick of RAM needed to be identified as faulty.

## Next setup stages

The next stage of RAMSim 2.0 was importing and connecting the scripts that control:

* RAM stick identity
* RAM socket detection
* randomised RAM insertion sounds
* POST LED feedback
* monitor boot video playback
* power button boot logic
* out-of-bounds RAM reset behaviour
