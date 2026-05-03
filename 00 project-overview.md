# Project Overview

## Project description

**RAMSim** is a VR game which recreates the satisfying sounds of installing computer components, along with the realistic frustrations that come with troubleshooting them.

The player is tasked with deducing the correct sequence for installing sticks of RAM into a giant motherboard. The game uses real recorded sounds of RAM being installed, as well as satisfying button presses, to make the interaction feel physical and responsive.

The main goal is to get the computer to boot successfully by finding the correct RAM configuration.

## Core concept

The game is based around a simple but deliberately awkward idea:

```
Pick up RAM
↓
Install RAM into the motherboard
↓
Press the power button
↓
Watch the POST lights
↓
Listen to the feedback
↓
Work out what went wrong
↓
Try again
```

The puzzle is designed to feel like a strange VR version of troubleshooting a real computer. It is meant to be satisfying, but also slightly frustrating in the way real hardware problems often are.

## Player goal

The player must:

* pick up RAM sticks
* place them into the correct motherboard slots
* press the power button to test the setup
* use the lights and sounds as feedback
* identify the faulty RAM stick
* find the correct RAM sequence
* get the computer to boot

## Main interaction loop

The main interaction loop is:

```
Grab RAM stick
↓
Insert RAM into a slot
↓
Hear RAM click sound
↓
Press power button
↓
POST lights run
↓
Computer passes or fails
↓
Player adjusts RAM setup
```

This loop is repeated until the player finds the correct solution.

## Key features

RAMSim includes:

* VR hand/controller interaction
* grabbable RAM sticks
* socket-based RAM installation
* a pressable power button
* real recorded RAM insertion sounds
* randomised button press sounds
* POST LED feedback
* a monitor boot video
* reset behaviour for lost RAM sticks
* a staged puzzle based on RAM configuration

## Design direction

The project originally started as a broader spatial-audio-led VR idea, but the technical setup became too difficult and time-consuming for the available development time.

The project was then refocused into a smaller and more achievable VR puzzle.

This was a useful design decision because it made the project more focused around one clear interaction:

```
Installing RAM into a motherboard
```

This gave the game a stronger identity and made it easier to develop, test, and improve.

## Why RAM?

The RAM idea came from a real issue I had with computer hardware, where RAM had to be installed in a particular sequence before the computer would work correctly.

This made it a good basis for a VR interaction because it combines:

* physical object handling
* problem solving
* repeated testing
* clear success or failure feedback
* satisfying mechanical sounds

## Universal design considerations

The brief asks for consideration of the Seven Principles of Universal Design. I used these as a way to think about how the interaction could be made clearer, more forgiving, and easier to understand.

| Universal Design Principle          | How I used it in the game design                                                                                                     |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Equitable Use                       | The main interaction is based on simple physical actions: pick up RAM, place it in a slot, and press the power button.               |
| Flexibility in Use                  | The player can test different RAM combinations at their own pace and keep trying until they solve it.                                |
| Simple and Intuitive Use            | The game uses familiar objects such as RAM sticks, a motherboard, lights, a button, and a monitor.                                   |
| Perceptible Information             | Feedback is given through POST lights, RAM click sounds, button sounds, and the boot video.                                          |
| Tolerance for Error                 | RAM sticks can reset if they leave the playable area, so the player cannot permanently lose an important object.                     |
| Low Physical Effort                 | The interaction area is small and focused, with unnecessary movement systems such as teleportation, climbing, and grab move removed. |
| Size and Space for Approach and Use | The motherboard and RAM sticks are oversized so they are easier to see, grab, and place in VR.                                       |

## Overall aim

The aim of RAMSim was to turn a simple computer troubleshooting problem into a physical VR puzzle.

The final result is rough, but it demonstrates the main assignment requirements:

* interactive VR objects
* grabbable components
* triggers and socket events
* audio feedback
* visual feedback
* puzzle logic
* user testing
* iteration based on feedback
