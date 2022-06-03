# Headphone Calibration (forked)
This is a [PsychoPy](https://psychopy.org/) 'experiment', which aims to help you figure out what PsychoPy audio output value corresponds to a physical (i.e. produced by headphones/speakers) volume of 60dB. It was developed by Jason He (original version [here](https://github.com/HeJasonL/Open-source-Auditory-Tone-Detection-Task)) and modified by Lowe Wilsson.

## Running the 'experiment'
Note that you need a decibel (dB) sound pressure level (SPL) measurement device to be able to perform the calibration.

1. Install [Standalone PsychoPy](https://www.psychopy.org/download.html).
2. Download this project, by either using the green 'code' button and selecting 'Download ZIP', or by using `git clone` if you know Git.
3. Open up e.g. 'headphone_calibration.psyexp' with PsychoPy.
4. Click the cogwheel ('Edit experiment settings') icon, go to the 'Screen' tab, and insert specifications appropriate for your monitor(s) (if you haven't already, you also need to do setup in Monitor Center - please see the [PsychoPy documentation](https://www.psychopy.org/)).
5. Click the Play ('Run experiment') icon.

Instructions will be displayed before calibration begins.

Once you've run the calibration you will be presented a value. Write down this value and copy it to the Auditory Tone Detection Task's configurations (see that experiment's README for further information).

## Differences from original
In the original version of the 'experiment', there are some testing site-specific instructions which have been removed/replaced here. Moreover, the original asks calibration to be done such that the reference volume is 113dB, which is very loud. In this modified version, the reference volume is set to 60dB, mainly because this increases calibration accuracy. The decision to not go lower than 60dB was mainly based on the not well sound-isolated testing environment used for a study at Karolinska Institutet that the modifications were done for. This meant that low volume ambient noise made calibration unreliable for lower dB reference values. 

If you have an anechoic chamber or similar very well isolated testing environment, you can likely achieve better accuracy by using a lower (e.g. 25dB) calibration volume. If you wish to do this, you need to replace all references to 60dB in this 'experiment' as well as the Auditory Tone Detection Task experiment. This is unfortunately a bit of a hassle, as such references are spread throughout the experiments.
