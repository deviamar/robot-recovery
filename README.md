# Robots Learning to Recover

Videos from my robot experiments on what a learned policy does after a mistake, and how
corrections and retraining changed that.

Static site, no build step. Published with GitHub Pages at
https://deviamar.github.io/robot-recovery/

## Add the headset photo

The "Showing the robot what to do" section has an optional slot for a photo of me in the VR
headset. Save it as `assets/img/teleop_photo.jpg` and it appears. While the file is missing,
the slot is hidden.

## Regenerate the two dataset clips

`demo_ep0` and `correction_ep90` are cut from the recorded flower dataset by
`/home/devi/deviamar.github.io/tools/recovery/encode_supplement_clips.sh`.

## Preview locally

    cd /home/devi && python3 -m http.server 8000
    # open http://localhost:8000/robot-recovery/

## Publish

    cd /home/devi/robot-recovery
    git add -A && git commit -m "Robots Learning to Recover"
    gh repo create deviamar/robot-recovery --public --source /home/devi/robot-recovery --push
    gh api -X POST repos/deviamar/robot-recovery/pages -f "source[branch]=main" -f "source[path]=/"

The page goes live at https://deviamar.github.io/robot-recovery/ a minute or two later.
