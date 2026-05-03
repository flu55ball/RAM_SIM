# 07 Changes made from testing and future improvements

This page explains the main changes made after testing and feedback.

The feedback showed that the game concept worked, but that the interaction, clarity, and feedback needed to be improved.

## Main feedback themes

The main feedback themes were:

* players liked the core concept
* players liked the sound design and physical RAM interaction
* players found the puzzle confusing without help
* players wanted clearer instructions
* players wanted clearer labels and indicators
* players needed better feedback when a puzzle stage was completed
* some objects could be lost or moved too far away
* the RAM sometimes felt awkward to hold in the earlier version

## Change 1: clearer project focus

The game was refocused around the strongest part of the experience: the physical act of picking up RAM, placing it into a motherboard, and testing the result.

Earlier versions had broader ideas around exploration and scavenger-hunt-style gameplay.

The updated version focused more directly on:

* RAM interaction
* socket placement
* power button testing
* POST light feedback
* boot video reward

## Change 2: improved RAM grabbing

Feedback showed that held RAM pieces could feel awkward or too close to the camera.

The RAM grab setup was adjusted using:

* XR Grab Interactable settings
* attach points
* Rigidbody settings
* smoothing
* grab distance tuning

This made the RAM sticks easier to pick up, hold, and place.

## Change 3: improved RAM socket interaction

The RAM slots were set up as socket interactors.

This allowed the RAM sticks to snap into place and made the puzzle more readable.

The socket system also allowed the game to track:

* which RAM stick was inserted
* which slot it was inserted into
* whether the inserted RAM was working or faulty

## Change 4: added reset behaviour

Earlier feedback mentioned RAM being lost behind the desk or objects being moved too far away.

A reset system was added so RAM could return to a reset point if it left the playable area.

This helped prevent the player from breaking the puzzle by losing an important RAM stick.

## Change 5: improved audio feedback

Players responded positively to the RAM clicking sounds and physical sound feedback.

The game uses recorded RAM insertion sounds and randomises the sound slightly each time.

This made repeated interactions feel more satisfying and less artificial.

## Change 6: added button and boot feedback

The power button was set up as the main test trigger.

When pressed, it:

* plays a button sound
* triggers a button animation
* starts the POST sequence
* checks the RAM configuration

The boot video gives the player a clear final reward when the puzzle is solved.

## Change 7: improved visual feedback

The POST LEDs were used to give visual feedback.

The lights show whether the computer is passing or failing its checks.

The feedback showed that the lights and labels still need to be as clear as possible, so this became one of the main areas to improve.

## Change 8: clearer instructions and onboarding

Testing showed that players needed clearer instructions.

The planned improvements are:

* add a controls screen
* add a goal screen
* make the instruction paper clearer
* make RAM labels easier to read
* explain the meaning of the POST lights more clearly
* give clearer feedback when a stage is completed

## Change 9: debug and polish fixes

Feedback also showed some smaller polish issues.

These included:

* turning off the debug menu
* correcting the light order
* improving performance where possible
* making the RAM labels bigger and clearer

## Summary

The testing confirmed that RAMSim works best as a physical VR puzzle built around satisfying interaction.

The main improvements were focused on:

* making RAM easier to grab
* making socket placement more reliable
* making sound feedback more satisfying
* making the game harder to break
* making the boot result clearer
* improving instructions and feedback

The next round of improvements should focus on making the puzzle rules and stage feedback clearer for first-time players.

***

## Future improvements

This page outlines the main improvements I would make if I had more time to continue developing RAMSim.

## Add a title screen

The first big improvement I would make is adding a proper title screen to the game.

This would make the game feel more complete before the player enters the main interaction.

A title screen could include:

* the game title
* a short description of the objective
* a start button
* a controls button
* a simple visual introduction to the RAM repair idea

This would help the player understand that they are entering a deliberate game experience, rather than just being dropped into a test scene.

## Add in-game instructions

The second major improvement would be adding in-game instructions.

I created an instruction PDF, but I did not get time to properly build those instructions into the game itself.

In hindsight, the time to reward did not really make sense.

The player was being asked to understand:

* VR movement
* VR grabbing
* RAM placement
* the power button
* motherboard POST lights
* the staged puzzle logic
* the idea of a faulty RAM stick

That is quite a lot to understand before getting a clear reward.

## Improve the time to reward

The game asks the player to do several things before they get the satisfaction of the computer booting.

In hindsight, the time to reward was probably too long.

A better version would give the player small rewards earlier, such as:

* a sound when they first pick up RAM
* a clear click when RAM is inserted
* a green light when the first correct pair is placed
* a message when a stage is completed
* a clearer fail sound when the wrong RAM is installed

This would make the puzzle feel less confusing and more readable.

## Make the game work as a tutorial

Perhaps the game could have even just been a tutorial.

This might have been a stronger introduction to game design.

Instead of trying to make a full puzzle straight away, the game could have focused on teaching one interaction at a time:

```
Pick up RAM
↓
Insert RAM into one slot
↓
Press the power button
↓
Watch one LED respond
↓
Try a second stick
↓
Learn what faulty RAM means
```

This would still use all the same systems, but the player would learn them more gradually.

## Improve puzzle onboarding

The puzzle rules need to be introduced more clearly.

A future version could include:

* a short tutorial sequence
* clearer instruction paper
* larger RAM labels
* clearer motherboard labels
* a visual guide to the RAM slots
* a warning that one RAM stick is faulty
* better stage completion feedback

The goal would be to keep the puzzle awkward and funny without making it feel broken or impossible to understand.

## Improve feedback when something is correct or incorrect

Testing showed that feedback was better than before, but still not clear enough for everyone.

The next improvement would be making it much clearer when the player has done something right or wrong.

For example:

```
Correct first pair
-> CPU and DRAM lights pass
-> short success sound
-> small message: "Memory pair detected"

Faulty RAM inserted
-> DRAM light flashes red
-> failure sound
-> small message: "Memory fault detected"
```

This would help the player understand the puzzle without fully giving away the solution.

## Keep the slow frustrating pacing, but make it feel intentional

The game is meant to be a little bit slow and frustrating.

That is part of the joke.

It is a VR game about troubleshooting RAM, so some awkwardness makes sense.

However, the frustration should feel intentional rather than accidental.

A future version should make sure the player always knows:

* what they are trying to do
* what just happened
* whether the computer passed or failed
* what part of the system is causing the issue

## Final reflection

The biggest future improvement would be clearer onboarding.

The core interaction works best when the player understands the basic loop:

```
Pick up RAM
↓
Slot RAM into the motherboard
↓
Press the power button
↓
Read the feedback
↓
Adjust the RAM setup
↓
Try again
```

If I continued developing the project, I would focus less on adding more mechanics and more on teaching the existing mechanics properly.

The game could probably work best as a short, funny, frustrating tutorial-style puzzle about fixing a computer.
