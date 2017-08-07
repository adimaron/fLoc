# fLoc
Functional localizer experiment used to define category-selective cortical regions

* * *
*Technical notes:*

The code in this repository is written in MATLAB (https://www.mathworks.com/)[MATLAB] (compatible with R2013a and later versions) and calls (http://psychtoolbox.org/)[Psychtoolbox-3] functions.
* * *

## Experimental Design

This repository contains stimuli and presentation code for a functional localizer experiment used to define category-selective cortical regions that respond preferentially to faces (e.g., fusiform face area), places (e.g., parahippocampal place area), bodies (e.g., extrastriate body area), or printed characters (e.g., visual word form area). 

The localizer uses a mini-block design in which 12 stimuli of the same category are presented in each **6 second block** (500 ms/image). For each **4 minute run**, a novel stimulus sequence is generated that randomizes the order of five stimulus conditions (faces, places, bodies, characters, and objects) and a blank baseline condition. We recommend collecting at least **4 runs of data** per subject (16 minutes total) to have sufficient power to define these and other regions of interest.

### Stimulus Conditions

Each of the five stimulus conditions in the localizer is associated with two related stimulus sets (144 images per set):

| Bodies | Example images    |                   |                   |                   |                   |
| ------ |:-----------------:|:-----------------:|:-----------------:|:-----------------:| -----------------:|
| body   | ![body-1][body-1] | ![body-2][body-2] | ![body-3][body-3] | ![body-4][body-4] | ![body-5][body-5] |
| limb   | ![body-1][body-1] | ![limb-2][limb-2] | ![limb-3][limb-3] | ![limb-4][limb-4] | ![limb-5][limb-5] |

[body-1]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/body-1.jpg "body-1.jpg"
[body-2]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/body-2.jpg "body-2.jpg"
[body-3]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/body-3.jpg "body-3.jpg"
[body-4]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/body-4.jpg "body-4.jpg"
[body-5]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/body-5.jpg "body-4.jpg"

[limb-1]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/limb-1.jpg "limb-1.jpg"
[limb-2]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/limb-2.jpg "limb-2.jpg"
[limb-3]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/limb-3.jpg "limb-3.jpg"
[limb-4]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/limb-4.jpg "limb-4.jpg"
[limb-5]: https://github.com/VPNL/fLoc/blob/master/stimuli/body/limb-5.jpg "limb-5.jpg"


- Bodies
    + body — whole bodies with cropped heads
    + limb — isolated arms, legs, hands, and feet
- Characters
    + word - pronounceable English pseudowords
    + number - uncommon numbers
- Faces
    + adult - portraits of adult faces
    + child - portraits of child faces
- Objects
    + car - four-wheel motor vehicles
    + instrument - musical string instruments
- Places
    + house - outdoor views of buildings
    + corridor - indoor views of hallways

#### Task

To ensure that participants remain alert and attentive throughout the experiment, a task is selected while executing the localizer. Three options are available:

- 1-back - detect back-to-back image repetition
- 2-back - detect image repetition with one intervening stimulus
- Oddball - detect replacement of a stimulus with scrambled image

Task probes (i.e., image repetitions or oddballs) are inserted randomly in half of the stimulus blocks. By default participants are alloted 1 second to respond to a task probe, and responses outside of this time window are counted as false alarms. Behavioral data displayed at the end of each run summarize the hit rate (percentage of task probes detected within the time limit) and the false alarm count (number of responses outside of task-relevant time windows) for the preceding run.

## Instructions

Follow the instructions below to first setup the code for your computers/equipment and then run the localizer.

### Setup

1. Navigate to the functions directory (`~/fLoc/functions/`)
2. Modify input registration functions for keyboard, button box, and trigger:
    - *get_keyboard_num.m* - Change value of `keyboard_id` to the "Product ID number" of your local keyboard (line 9)
    - *get_box_num.m* - Change value of `box_id` to the "Product ID number" of the button box used at your scanner facilities (line 9)
    - *start_scan.m* - Change specifications to be compatible with your local trigger box (line 6)
3. Add Psychtoolbox to your MATLAB path.

### Execution

1. Navigate to base experiment directory in MATLAB (`~/fLoc/`).
2. Execute the `runme.m` wrapper function.
3. Enter subject initials when prompted.
4. Select triggering option:
    - Enter `0` if not attempting to trigger scanner (e.g., while debugging)
    - Enter `1` to automatically trigger scanner at onset of experiment
4. Select task for participant:
    - Enter `1` for 1-back image repetition detection
    - Enter `2` for 2-back image repetition detection
    - Enter `3` for oddball detection
5. Wait for task instructions screen to display.
6. Press `g` to start experiment (and trigger scanner if option is selected).
7. Wait for behavioral performance to display after each run.
8. Press `g` to continue experiment and start execution of next run.

### Debugging

- Press `[Command + period]` to halt experiment.
- Enter sca to return to MATLAB command line.
- Please report bugs on GitHub.

## Code





## Analysis

## Citation
