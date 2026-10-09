# Verification

Checked on one Windows computer with Unity 6000.5.10f1 on 9 October 2026. Phone-shaped layout does not establish Android or iOS compatibility.

## Final portrait build

The final Windows build succeeded in 8.798 seconds. Its 405-by-720 client area has all eight labels and four status labels visible. All eight buttons were pressed in the final executable. Feed, Love, Play, Study, Sleep, Wash, and Drink showed their corresponding animation and documented bar feedback. Scene switched bedroom to garden and back while preserving bar values.

Study initially had its book hidden by the table. The table was lowered and shortened, then the open book was observed above its surface. The longest speech text initially ran past the bubble. The bubble was widened and all eight messages were observed fitting inside it in the final build.

Feed has a bone and food bowl; Study has a table and book; Sleep has a bed; Wash has a tub and bubbles; Drink has a water bowl. Speech and transient props disappeared after the action interval. The Scene speech was explicitly checked after a four-second wait and was hidden, with the pet idle.

Actual build screenshots are under docs/img/portrait-*.png. They are captures, not design mockups. Each client image is 405 by 720.

The Windows ZIP contains 199 entries and is 45,114,270 bytes. Its archive integrity check passed. A fresh extraction launched successfully, with its executable matching the built file. Three rapid clicks on Wash showed washing, the correct speech bubble, and full cleanliness without an error. Returning to idle was checked afterward.

## Frames and scripts

There are 96 new transparent frames: eight states with twelve distinct 192-by-192 PNGs each. Every imported frame is checked against the matching separate sprites-repo file. Clips are configured at 12 frames per second. Original source frames are preserved.

Exactly three C# files exist under Assets and each SHA-256 matches PocketPet/Game/Assets/Scripts. No helper or editor scripts were added.

| Script | SHA-256 |
| --- | --- |
| AudioManager.cs | 61285E68144C6910362E61274F6DFEFE6E34D81EA1934EECF74FB47A5BA5CFC8 |
| PetButtons.cs | 859C44EF202D52B5941D7D64F5F8DA0BB7A57472754D9BF7BA4BBDBA320DC566 |
| Sound.cs | 0B3656EB5F98ABF6BC1E336600B723DCD37A138847C08FC114B099DD8A133A7D |

All eight buttons call configured sound names. The three WAV files contain nonzero PCM samples: food peak 14200, love peak 14627, play peak 17564 on the 16-bit scale. The final player log contained no exceptions or errors. Speaker output has not been independently recorded or heard.

## Limits

The original optional Runtime Pipeline package remains disabled because no RuntimePipelineConfig was supplied. Unity reports a ComputeBuffer disposal message on player exit. The rendered game and interactions were checked despite these package diagnostics.

Keyboard navigation, Android, iOS, Mac, and Unity 6000.2.2f1 are untested. Automatic needs decay and saved progress are absent. The bars are session-only action feedback. Smoothness has not been compared in a measured motion study; twelve-frame clips and visible pose changes are verified.
