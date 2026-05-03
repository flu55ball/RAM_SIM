# 02 Puzzle logic and win condition

This page explains the RAM puzzle rules and how the player wins the game.

## Purpose of the puzzle

The player must work out which RAM stick is faulty and place the working RAM into the correct motherboard slots.

The player tests each setup by pressing the power button.

The computer gives feedback using:

* POST LEDs
* RAM insertion sounds
* button press sounds
* monitor boot video

## RAM stick identities

The game uses six RAM sticks:

```
RAM_16_A_OK
RAM_16_B_OK
RAM_16_C_OK
RAM_16_D_BAD
RAM_8_A_OK
RAM_8_B_OK
```

## Faulty RAM

One RAM stick is faulty.

```
Faulty RAM: RAM_16_D_BAD
```

If the faulty stick is installed, the computer fails the boot check.

## Active motherboard slots

The motherboard uses four active RAM slots:

```
DIMM_A1
DIMM_A2
DIMM_B1
DIMM_B2
```

The correct paired slots are:

```
DIMM_A2 + DIMM_B2
```

This is based on how real motherboards often recommend using paired RAM slots.

{% stepper %}
{% step %}
### Stage 1

The first stage teaches the player the correct RAM pair.

```
Required:
├── two RAM sticks installed
├── both must be 16GB
├── both must be working
└── they must be in DIMM_A2 and DIMM_B2
```

The player must:

* insert two working 16GB RAM sticks
* place them in `DIMM_A2` and `DIMM_B2`
* press the power button to test

If correct, stage 1 passes.
{% endstep %}

{% step %}
### Stage 2

The second stage builds on the first stage.

```
Required:
├── keep the DIMM_A2 and DIMM_B2 pair
├── add one more working 16GB stick
└── total = three 16GB sticks
```

The player must:

* keep the working `DIMM_A2` and `DIMM_B2` pair
* add one more working 16GB RAM stick
* press the power button to test

If correct, stage 2 passes.
{% endstep %}

{% step %}
### Final stage

The final stage adds an 8GB stick.

```
Required:
├── keep the working 16GB setup
├── add one working 8GB stick
├── total = three 16GB sticks and one 8GB stick
└── no faulty RAM installed
```

The player must:

* keep the three working 16GB RAM sticks installed
* add one working 8GB RAM stick
* avoid the faulty RAM stick
* press the power button

If correct, the computer boots.
{% endstep %}
{% endstepper %}

## Feedback rules

```
Green LED = check passed
Red LED = check failed
DRAM flashing red = RAM problem
Boot video plays = final success
```

## Win condition

The player wins when the correct final RAM setup is installed and the boot video plays on the monitor.

```
Correct final setup
↓
Power button pressed
↓
POST sequence runs
↓
RAM configuration passes
↓
Monitor plays boot video
↓
Player has fixed the computer
```

## Player-facing explanation

A simple explanation for the player would be:

```
The computer will not boot.
One RAM stick is faulty.
Test different RAM combinations by inserting sticks into the motherboard and pressing the power button.
Use the lights and sounds to work out which RAM stick is causing the problem.
```
