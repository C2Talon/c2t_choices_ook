# Summary
A kolmafia choice adventure script to automate and track the "Ook the Mook" choice adventure chain in the Time-Twitching Tower.

# Usage
Will need to set the preference `choiceAdventureScript` to `c2t_choices_ook.ash` when you want to make use of this. And then unset it, or set it to a different one, when you don't.

The preference `c2t_ttt_ookTheMookCurrentAscension` stores the last ascension the script was triggered on. The preference is used to detect whether any part of the chain was started in the current ascension with the script. If its value is less than `my_ascensions()`, then this script hasn't triggered during this ascension and the value of `c2t_ttt_ookTheMookStage` should not be presumed to be correct. If `c2t_ttt_ookTHeMookCurrentAscension` is equal to `my_ascensions()`, then `c2t_ttt_ookTheMookStage` should be correct.

The chain progress is tracked with the preference `c2t_ttt_ookTheMookStage`. At `0` to `3`, the quest is as of yet unfinished and will need to do the chain again to progress. At `4` everything is finished, the choice adventure chain will be unavailable from that point on, and Caveman Dan is available to fight. After fighting and winning against Caveman Dan, you may want to set `c2t_ttt_ookTheMookStage` to `5` or higher for your own tracking purposes in your own driver script.

This choice adventure script requires some sort of driver script to actually go to the places neccessary to trigger the ability to go to the choice adventure and to trigger the choice adventure script. And then to go and actually fight Caveman Dan afterwards.

Alternatively, can adventure manually up to the choice adventure's start, but will need to click the `auto` button at the top when the choice adventure is at its initial dialog. Doing any part of chain without the script will cause it to get lost, since it won't be able to update its tracking. There is some self-correction to try to figure out where it is in some of those cases, but there may be edge cases not accounted for. In short, don't do the choice adventure chain manually if you want this choice adventure script to work.

# Installation
In the kolmafia gCLI:

`git checkout https://github.com/C2Talon/c2t_choices_ook.git master`
