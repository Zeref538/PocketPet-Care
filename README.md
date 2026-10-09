# PocketPet Care

A portrait virtual-pet care demo built in Unity 6000.5.10f1 with only three supplied scripts, unchanged.

![Portrait layout in the earlier v1.1.0 Windows build](docs/img/portrait-study.png)

Download the [complete Unity project](https://github.com/Zeref538/PocketPet-Care/archive/refs/heads/main.zip), extract it, and add the extracted folder in Unity Hub. The older v1.1.0 executable does not include this source update.

## Play

Eight buttons share one glossy shape, with different colors and a pup performing each action. Each action shows a short speech bubble, plays a supplied sound and an action music cue, and returns to idle after three seconds.

| Button | What appears | Status feedback |
| --- | --- | --- |
| Feed | Bone biscuit and food bowl | Hunger 100%, happiness 85% |
| Love | Happy pup | Happiness 100% |
| Play | Pup and red ball | Happiness 95%, hunger 40%, energy 35%, cleanliness 40% |
| Study | Glasses, open book, wooden table | Energy 45%, hunger 50%, happiness 70% |
| Sleep | Sleeping pup in a pink bed | Energy 100%, hunger 35%, happiness 75% |
| Wash | Pup washing in a tub with bubbles | Cleanliness 100%, happiness 85% |
| Drink | Pup lapping from a water bowl | Energy 80%, happiness 80% |
| Scene | Bedroom or garden | Existing values preserved |

Idle and the seven care states each use twelve distinct sprite frames at 6 frames per second, with a two-second loop. The pup pixels are opaque while the surrounding canvas stays transparent. Scene crossfades between bedroom and garden over 0.6 seconds. Speech bubbles and extra props disappear at idle.

The bars show fixed action feedback; bars not listed for an action stay unchanged. A full hunger bar means well fed. A soft 24-second background melody loops continuously, with eight distinct three-second action motifs. Repeating a button restarts its motif; changing actions stops the previous motif. These are original synthesized instrumental clips.

The action values are presets rather than changes relative to the current value. Automatic needs decay, sickness, death, and saved progress are absent. Restarting resets bars to 55% and restores the bedroom. Sad and Cry remain unused source animation clips; they are no longer action buttons.

## Edit

Add this repository root in Unity Hub with Unity 6000.5.10f1. Open Assets/Scenes/SampleScene.unity and choose a 9:16 aspect ratio in the Game view before pressing Play. The standalone window defaults to 405 by 720; the Canvas reference is 720 by 1280.

Build profiles are local to each computer and are not shared. The scene remains in the global build scene list. A Windows-only profile was removed because editors without its WindowsPlatformSettings type reported a missing-type warning.

Unity 6000.2.2f1 installation failed on the authorized retry because Windows administrator approval was unavailable. This project uses the authorized 6000.5.10f1 fallback. Older-editor compatibility and Mac builds are untested.

Artwork is available separately in [PocketPet-sprites](https://github.com/Zeref538/PocketPet-sprites). The artwork can be downloaded without Unity project files.

Runtime source is limited to PetButtons.cs, AudioManager.cs, and Sound.cs. Two instances of the unchanged PetButtons drive the pet and speech-bubble timers. Built-in Animator and Button events handle props and scenery. No helper or editor scripts are included. See [verification](docs/VERIFICATION.md).
