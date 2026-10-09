# Scene data

PetButtons holds the pet Animator and a three-second idle timer. Animator Mood selects idle 0, happy 1, sad 2, crying 3, eating 4, playing 5, studying 6, and sleeping 7.

The portrait revision adds washing 8 and drinking 9. A second PetButtons instance drives the UI Animator using the same action values and scenery speech at 10. A separate background Animator uses the Next trigger to toggle bedroom and garden. Sad and crying are preserved source states without buttons.

AudioManager stores named Sound entries referencing AudioClips. Every button sound must match a configured name. UI components hold transient status values; there is no database or save file.
