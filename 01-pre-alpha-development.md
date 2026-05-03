# 01 pre alpha development

These notes are reconstructed from the original video report, so they focus on the main setup issues rather than every exact troubleshooting step.

## Original spatial audio plan

* The original idea was to use spatial audio as a major part of the game.
* The plan was to use the Pico spatial audio demo as a basis for this.
* The game idea at that stage was “some sort of spatial audio based game where you'd have to go through the level and fix the scale and maybe have kind of sound based prompts where you'd kind of pick up key cards and have to open doors and explore the area.”
* However, the setup generally became too much of an issue.
* Because of this, the project moved away from spatial audio as the main mechanic.
* Audio was kept as an important part of the game, but more as interaction feedback than as the central navigation system.

## Spatial audio demo setup issues

* I brought the level into Unity “after so much hassle setting up the special audio demo.”
* The first issue was “it not launching at all, like Unity not launching at all.”
* I fixed that “by I think uninstalling and reinstalling Unity multiple times.”
* I had originally manually set up the XR system myself, “but it got lost in in the various versions of trying to get the the demo working.”
* I ended up using the XR setup from the demo because it was already working.
* The demo had useful parts, including the way it organised sound sources and centralised sounds through an audio manager script.
* However, the time spent getting the demo working made it harder to focus on the actual game mechanics.

## Android and Unity build issues

* I had “an issue building it.”
* I was “getting an error where Android it was claiming Android 13 wasn't installed and it wasn't allowing it to be installed.”
* This was fixed “by uninstalling Unity,” but I also “needed to fix the Java home directory within the the Windows environment variable.”
* Getting Android Studio working became part of the setup process.
* I was eventually “able to actually emulate the the Pico.”
* When exporting for “the pico the non pro,” it would not work.
* I had to “spend ages down grading it back to Android 10.”
* This was done through Android Studio.
* I also had to “maybe manually paste in the SDKS into the Unity directory.”
* Overall, “it was very awkward.”
* Eventually I got it working.

## Ongoing Pico / emulator issues

* There was an ongoing issue where “if you connect to the Internet, there's an authentication error.”
* I did not know what caused it at the time.
* The emulator “didn't like Vulcan.”
* I was also working with “a slightly weird version of the Pico SDK.”
* This was marked as “an ongoing issue that needs to be fixed.”

## How this changed the project direction

* The project became too difficult to manage while also trying to solve the spatial audio demo setup.
* The game direction changed from a wider spatial audio scavenger hunt into a smaller interaction puzzle.
* The idea “went a little bit from more of a scavenger hunt to more of a kind of satisfying, satisfying itch ish SMR kind of puzzle game.”
* This helped reduce the scope and made it easier to focus on a working VR interaction.
* The final pre-alpha direction became a RAM puzzle based around:
  * picking up RAM sticks
  * placing them into slots
  * pressing a power button
  * using audio feedback
  * finding the correct sequence
  * identifying a faulty stick of RAM
