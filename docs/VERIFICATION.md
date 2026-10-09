# Verification

Checked on Windows with Unity 6000.5.10f1 on 9 October 2026. These checks cover one computer, not the Mac lab or a phone build.

## Gameplay

All eight buttons were pressed in Unity Play mode. Feed showed eating and filled hunger; Play showed the ball animation; Study showed the book animation; Sleep showed sleeping and filled energy. Sad and Cry showed their respective expressions and lowered happiness. Love and Wash invoked happy and updated happiness and cleanliness respectively.

Four bars rendered correctly. Each changed to its documented fixed value. The pet returned to idle after the action interval. The Console showed zero errors and zero warnings after the eight-action Play-mode check.

The scene contains eight PetButtons calls, eight AudioManager calls, and eight Image.fillAmount calls. All buttons use their configured sound name. The three WAV files contain nonzero PCM samples: food peak 14200, love peak 14627, and play peak 17564 on the 16-bit scale. Button tests produced no missing-sound exceptions. This verifies the assets and playback wiring; speaker output has not been independently recorded or heard.

## Supplied scripts

Exactly three C# files exist under Assets. Each SHA-256 matches the supplied file in the source PocketPet project. No helper or editor scripts were added.

| Script | SHA-256 |
| --- | --- |
| AudioManager.cs | 61285E68144C6910362E61274F6DFEFE6E34D81EA1934EECF74FB47A5BA5CFC8 |
| PetButtons.cs | 859C44EF202D52B5941D7D64F5F8DA0BB7A57472754D9BF7BA4BBDBA320DC566 |
| Sound.cs | 0B3656EB5F98ABF6BC1E336600B723DCD37A138847C08FC114B099DD8A133A7D |

## Build and limits

Windows builds succeeded and the executable launched. The original 1920-by-1080 window clipped labels on this screen. The final configuration uses a 1280-by-720 window and disables the native-resolution override.

The final build succeeded in 8.275 seconds. All eight buttons were also pressed in the final Windows executable, with their animations and bar changes observed. All eight labels were visible. The preview is an actual 1280-by-720 capture after these interactions, with the pet back at idle.

The final player log contained no exceptions. On exit Unity reported a ComputeBuffer disposal message from the rendering stack. Keyboard navigation and physical speaker output remain unverified.

The Windows release ZIP is 44,974,695 bytes. Its 199 entries include the executable, its data folder, Mono runtime, and UnityPlayer.dll. GitHub accepted the release upload. The executable was tested before packaging; a fresh extraction has not been retested.

Unity emitted one package warning during building: no RuntimePipelineConfig asset was found, so the optional Runtime Pipeline is disabled in player builds. The care scene still rendered and ran. This is recorded rather than hidden.

Unity 6000.2.2f1 installation failed on the authorized retry because administrator elevation was unavailable. The authorized 6000.5.10f1 fallback was used. Older-editor compatibility and Mac builds remain untested.

Automatic needs decay and saved progress are absent. The status bars demonstrate action feedback through built-in components. Wash reuses happy because no wash animation was supplied.
