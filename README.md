# Robots Learning to Recover

Videos and images supplementing my paper "Helping Robots Recover From Their Mistakes".

Static site, no build step. Published with GitHub Pages at
https://deviamar.github.io/robot-recovery/

## Add the headset photo

The "Recording demonstrations" section has an optional slot for a photo of me in the VR
headset. Save it as `assets/img/teleop_photo.jpg` and it appears. While the file is missing,
the slot is hidden.

## Regenerate the two dataset clips

`demo_ep0` and `correction_ep90` are cut from the recorded flower dataset by
`/home/devi/deviamar.github.io/tools/recovery/encode_supplement_clips.sh`.

`base50_missed_grasp` is rollout `20260912_194930_ep06` (policy trained on the first 50
demos), cropped to the low + wrist tiles like the other rollout clips in `encode_clips.sh`.

`assets/img/start_grid.jpg` is a crop of `flower_start.jpg` with a 3x3 grid drawn over the
area of the dense start cluster in `placements_128.jpg` (same camera, scaled 640 -> 1012).

## Preview locally

    cd /home/devi && python3 -m http.server 8000
    # open http://localhost:8000/robot-recovery/

## Publish

    cd /home/devi/robot-recovery
    git add -A && git commit -m "Robots Learning to Recover"
    gh repo create deviamar/robot-recovery --public --source /home/devi/robot-recovery --push
    gh api -X POST repos/deviamar/robot-recovery/pages -f "source[branch]=main" -f "source[path]=/"

The page goes live at https://deviamar.github.io/robot-recovery/ a minute or two later.
