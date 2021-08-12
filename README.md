# menuInUnity
 A menu scene and an in-game menu. Works with the repo about AudioManager.

 DISCLAIMER : We will do just the basic of a menu for a PC game (fullscreen toggle, resolution). No design, just buttons.

Original video tutorial by TUTO UNITY FR alias zef, on youtube :
https://www.youtube.com/channel/UCJRwb5W4ZzG43J5_dViL6Fw
https://github.com/TUTOUNITYFR

 -----------------
 MANUAL :
 -----------------

1. Make a new scene called mainMenu.

2. Set the bg color of the main camera to black.

3. Add a new button, also making by this action a Canvas.

4. Re-size it and place it a little bit higher than the middle. 

5. Do 2 clones of this button, ones on the others, making a vertical line of 3 buttons.

6. Name the buttons "Continue", "Settings", "Exit".

7. Add to the Canvas a script named "mainMenu".

8. Make a new panel named "SettingsWindow".

9. Anchor to the middle, and re-size it to the width of your buttons with some padding.

10. Add to your panel : a Dropdown, a Toggle, a Slider.

11. Re-size your new components.

12. Remove the text for the toggle, resize its borders (unity borders of the object) to only the checkbox.

13. Make 3 new texts :
    - RESOLUTION : In front of the Dropdown.
    - FULLSCREEN : In front of the Toggle.
    - VOLUME : In front of the slider.

14. Set slider's max value to 0, min value to -80. (no mistake)

15. Add to SettingsWindow (the panel) a new script "settingsMenu" open it so we can go back to him later.

16. Open a new window in Unity "Window/Audio/Audio Mixer".

17. Add a new mixer name "mainMixer".

18. Select "Master" and, in its Inspector parameters, do a left click on "Volume" and click "Expose volume [...]"

19. Return in your Audio Mixer to click on the top right of it where the list "Exposed Parameters" is located. Rename "MyExposedParam" to "volume".

20. Time go back to our opened "settingsMenu" script to copy-paste the code located in the "PCBasedMenu" in the github repo.

21. Return to Unity and add to the script (attached to SettingsWindow I remember you) the reference of "Audio Mixer" and "Dropdown.

(you can only test the next options with a unity build)

22. For the Toggle button in our window, add a new event for OnValueChanged (inspector) : drop the SettingsWindow script and select as function "SetFullScreen".

23. Go in the Dropdown and add a new event OnValueChanged : 
    - script : SettingsWindows.
    - function : SetResolution().

24. In the mainMenu script, type the name of the scene to load in "sceneToLoad".

25. Copy & Paste my code in your script.

26. Add a new event on your buttonSettings :
    - script : mainMenu (drag&drop Canvas).
    - function : SettingsButton().

27. Add a new event on your buttonStart :
    - script : mainMenu (drag&drop Canvas).
    - function : StartGame().

28. Add a new event on your buttonStart :
    - script : mainMenu (drag&drop Canvas).
    - function : QuitGame().

Everything should be working. We're now going to do a button to be able to close SettingsWindow.

29. Make a new button.

30. Re-size it and place to the top-right corner.

31. Add as text an "X".

32. Add a new event on your buttonStart :
    - script : mainMenu (drag&drop Canvas).
    - function : CloseSettingsWindow(). 

33. Desactivate settingsWindow.

34. Rename all your buttons, UI stuff correctly.

34. Build&Test ^^ !