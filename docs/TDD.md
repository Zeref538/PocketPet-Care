# Implementation

Reuse existing sprite animation clips and wire UI Button events to PetButtons.Play(int) and AudioManager.Play(string). Configure Image or Slider components for status feedback through built-in setters. Do not copy or run editor builders.

New C# controllers could implement a full care simulation but violate the supplied-script constraint. Configure existing components and scene assets instead. Check every action in Play mode, inspect Console errors, and compare all three script hashes with PocketPet.

The portrait revision adds twelve-frame sprite loops without adding scripts. PetButtons drives the pet Animator with Mood integers, including washing at 8 and drinking at 9. A second instance of the same unchanged component drives the speech bubble Animator and its three-second timer.

Button events set speech text and fixed status values through built-in UI setters. Pet animation clips show the study table, sleep bed, or food bowl for their corresponding states. Scene sends the Next trigger to a separate background Animator, toggling bedroom and garden without unloading the scene or resetting the bars.
