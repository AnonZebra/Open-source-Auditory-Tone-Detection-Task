# Auditory Tone Detection Task (forked)
 <img width="400px" src="example_images/atdt_intro_ex.png">

This is a modified version of the Open Source Auditory Tone Detection Task experiment developed by Jason He, with modifications and corrections made by Lowe Wilsson. The original version/repository can be found [here](https://github.com/HeJasonL/Open-source-Auditory-Tone-Detection-Task). The experiment is created with [PsychoPy](https://psychopy.org/).

## Experiment outline
In the experiment, participants go through 50 trials (this can be reconfigured). In each trial, the participant is shown two light bulbs, one on the left-hand side and one on the right-hand side. The light bulbs both light up, one at a time. At the same time as one of the light bulbs lights up, a tone is played. The participant is then asked to indicate (with keyboard keys '1'/'2') if the tone was played as the left or right bulb lit up. Throughout the experiment, the tone volume is increased/decreased based on the participant's performance.

At experiment startup, one may choose to activate 'masking', where a noise is played simultaneously ('Simultaneous') with the target tone, or directly after ('Backward') the target tone. One may also choose to not use any masking ('Quiet').

Task difficulty (tone volume) is updated based on the QUEST algorithm/method (Watson & Pelli, 1983).

## Running the experiment
1. Install [Standalone PsychoPy](https://www.psychopy.org/download.html).
2. Download this project, by either using the green 'code' button and selecting 'Download ZIP', or by using `git clone` if you know Git.
3. Open up e.g. 'pure_tone_detection.psyexp' with PsychoPy.
4. Click the cogwheel ('Edit experiment settings') icon, go to the 'Screen' tab, and insert specifications appropriate for your monitor(s) (if you haven't already, you also need to do setup in Monitor Center - please see the [PsychoPy documentation](https://www.psychopy.org/)).
5. Click the Play ('Run experiment') icon.

You will also need to change experiment configurations, e.g. the size of stimuli or number of trials. The number of trials is set in the 'welcome' routine's 'welcome_code' code component, while other configurations are made directly through the various PsychoPy components that are used.

## Pre-experiment calibration
Note that, for this experiment to run correctly, it is _absolutely necessary_ that you first run the Headphone Calibration PsychoPy 'experiment'. This calibration 'experiment' is included in the [GitHub code repository](https://github.com/AnonZebra/Open-source-Auditory-Tone-Detection-Task) (see the subdirectory 'Headphone Calibration'). The calibration should result in a value that's used, roughly, to inform PsychoPy what volume setting on the computer corresponds to producing 80dB sound through the physical speakers. This experiment extrapolates from the calibration information to produce sound at correct volumes.

Once you've run the Headphone Calibration 'experiment' and have a calibration value:
1. Open up 'pure_tone_detection.psyexp'.
2. Click the cogwheel icon.
3. In the 'Basic' tab, under 'Experiment info', update the 'Calibration' value.

## Translating the experiment
All experiment instructions are specified in a code component.

1. Open 'pure_tone_detection.psyexp'.
2. Go to the 'welcome' routine.
3. Open up the 'translation_code' component.
4. In the 'Before experiment' tab, insert your translations. (make sure to leave the apostrophes `''` and parentheses `()`).
    - You can find examples of translations in the 'translations' subdirectory.

Once you've finished translating the experiment, save it ('Save current experiment file' in main window toolbar) and try running it again.

## Output data
The most relevant output data files are the 'CSV'/'.csv' files, saved to the 'data' directory. The most important columns in these files are as follows:

* Trial: Trial number
    - _Note_ that the 'practice trials' are also given trial numbers 0-5, then trial counting restarts from 1 for the 'real' trials.
* Desired_dB: The decibel (dB) that was 'intended' to be played by PsychoPy for the corresponding trial.
    - In order to ensure that the physically produced volume corresponds to desired dB values, the experiment relies on a correct audio calibration/configuration of the experiment having been done (see 'Pre-experiment calibration').
* key_resp_trial.corr: indicates whether participant response was 'correct', 'incorrect', or there was 'no response' (for 'baseline' blocks, this column holds a 'baseline' value).

## Attribution
As mentioned above, this is a modified version of an experiment developed by Jason He, during collaboration with Nicolaas Puts. The code repository for this modified version can also be found [on GitHub](https://github.com/AnonZebra/Open-source-Auditory-Tone-Detection-Task). Modifications were made by Lowe Wilsson, while working for Janina Neufeld at Karolinska Institutet. As of yet, no article describing the experiment has been published. In the meantime, if you use this modified version in a study, please include links to both the [original](https://github.com/HeJasonL/Open-source-Auditory-Tone-Detection-Task) and this modified version's code repositories.

## Error reporting
If you notice any problems with the experiment even after following the instructions above, please create a GitHub issue on this project's [repository](https://github.com/AnonZebra/Open-source-Auditory-Tone-Detection-Task).

## References
Watson, A. B., & Pelli, D. G. (1983). Quest: A Bayesian adaptive psychometric method. Perception & Psychophysics, 33(2), 113–120. https://doi.org/10.3758/BF03202828
