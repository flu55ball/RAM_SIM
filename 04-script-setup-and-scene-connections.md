# 04 Script setup and scene connections

After setting up the project, the ChatGPT-generated scripts were imported into Unity and connected to the main objects in the scene.

The scripts control:

* RAM stick identity
* RAM socket detection
* randomised RAM insertion sounds
* POST LED feedback
* monitor boot video playback
* power button boot logic
* RAM reset behaviour if a stick leaves the playable area

The scripts were written by ChatGPT, but they were imported, assigned, tested, and adjusted inside Unity as part of the project setup.

## Scene hierarchy screenshot

The Unity hierarchy screenshot used for this setup reference is included in the `assets` folder.

## Scene setup overview

```
Main_room
├── XR Interaction Setup
├── Room
├── Motherboard
│   ├── CPU
│   ├── DRAM
│   ├── VGA
│   ├── BOOT
│   ├── RAM_Sockets
│   │   ├── DIMM_A1
│   │   ├── DIMM_A2
│   │   ├── DIMM_B1
│   │   └── DIMM_B2
│   ├── RAM
│   │   ├── RAM_16_B_OK
│   │   ├── RAM_16_C_OK
│   │   ├── RAM_16_A_OK
│   │   ├── RAM_16_D_BAD
│   │   ├── RAM_8_B_OK
│   │   └── RAM_8_A_OK
│   ├── Screen
│   ├── outofbounds
│   ├── RAM_Global_Reset_Point
│   ├── onbutton
│   │   └── power_001
│   └── PostBootController
```

The player interacts with the RAM and power button, while the `PostBootController` reads the socket information and controls the visual feedback, audio feedback, and final boot video.

***

## RamModule.cs

**Purpose:**\
Stores the identity, capacity, and condition of each RAM stick.

**Where it is used:**

```
Motherboard
└── RAM
    ├── RAM_16_B_OK      -> RamModule
    ├── RAM_16_C_OK      -> RamModule
    ├── RAM_16_A_OK      -> RamModule
    ├── RAM_16_D_BAD     -> RamModule
    ├── RAM_8_B_OK       -> RamModule
    └── RAM_8_A_OK       -> RamModule
```

**How it works:**

* Each RAM stick has a `moduleName`.
* Each RAM stick is set as either `GB8` or `GB16`.
* Each RAM stick can be marked as `isFaulty`.
* The `PostBootController` reads this information when checking the puzzle.

***

## RamSocketReporter.cs

**Purpose:**\
Tracks which RAM stick is currently inserted into each motherboard slot.

**Where it is used:**

```
Motherboard
└── RAM_Sockets
    ├── DIMM_A1 -> RamSocketReporter
    ├── DIMM_A2 -> RamSocketReporter
    ├── DIMM_B1 -> RamSocketReporter
    └── DIMM_B2 -> RamSocketReporter
```

**How it works:**

* Each socket has a slot ID.
* When RAM is inserted, the script checks the inserted object for a `RamModule`.
* It stores the currently inserted RAM stick.
* When the RAM stick is removed, it clears the slot.
* The `PostBootController` checks each socket to work out the current RAM configuration.

***

## RandomOneShotSpatial.cs

**Purpose:**\
Plays a random sound effect when an interaction happens.

**How it works:**

* It uses an `AudioSource`.
* It contains a list of audio clips.
* When triggered, it chooses one clip randomly.
* It slightly randomises the pitch each time.
* This stops repeated sounds from feeling too identical.

**Used for:**

* RAM insertion sounds
* power button press sounds
* making repeated interactions feel more natural

***

## PostLed.cs

**Purpose:**\
Controls the colour of each POST LED on the motherboard.

**Where it is used:**

```
Motherboard
├── CPU  -> PostLed
├── DRAM -> PostLed
├── VGA  -> PostLed
└── BOOT -> PostLed
```

**How it works:**

* Each LED object has a renderer.
* The script changes the material colour.
* The LED can be set to off, green, or red.
* The `PostBootController` tells each LED what colour to show during the boot sequence.

***

## MonitorScreenController.cs

**Purpose:**\
Controls the computer monitor screen and boot video.

**How it works:**

* At the start, the monitor is set to the off material.
* When the computer boots, the screen switches to the video material.
* The boot video starts from the beginning.
* This gives the player a clear success state.

***

## PostBootController.cs

**Purpose:**\
Controls the main boot sequence, POST LEDs, power button behaviour, and RAM puzzle logic.

**How it works:**

* The power button triggers the boot check.
* The POST LEDs run through a red and green sequence.
* The controller reads the four RAM sockets.
* It checks which RAM sticks are installed.
* It checks whether any faulty RAM is installed.
* It checks the staged puzzle rules.
* If the configuration is wrong, the DRAM LED flashes red.
* If the final configuration is correct, the boot video plays.

***

## ResettableRam.cs

**Purpose:**\
Allows RAM sticks to reset back to a global reset point if they leave the playable area.

**How it works:**

* Each RAM stick references `RAM_Global_Reset_Point`.
* If the RAM needs to reset, its velocity and rotation are cleared.
* It is moved back to the reset point.
* The script checks whether the RAM is currently being held so it does not reset while the player is grabbing it.

***

## OutOfBoundsResetZone.cs

**Purpose:**\
Detects when a RAM stick leaves the playable area and tells it to reset.

**How it works:**

* The out-of-bounds area uses trigger colliders.
* When something enters the trigger, it checks whether the object has a `ResettableRam` script.
* If it finds one, and the RAM is not being held, it sends the RAM back to the global reset point.
* This prevents the player from losing RAM pieces during the puzzle.
