# This fork only includes the Interception method from [TaranVH's original repository](https://github.com/TaranVH/2nd-keyboard), for the sake of creating a secondary [Aegisub](https://github.com/Ristellise/AegisubDC) typesetting keyboard.
--------------------------------------------------------------------
## TaranVH's install steps for interception, intercept, and AutoHotKey:
--------------------------------------------------------------------
### VIDEO TUTORIAL THAT EXPLAINS ALL THIS IN GREATER DETAIL:
https://www.youtube.com/watch?v=y3e_ri-vOIo

### DOWNLOADING INTERCEPTION:
- Navigate to this page:
- https://github.com/oblitum/Interception
- Click on "download the latest release."
- Click on Interception.zip to download it.
- Unzip the file to some location on your computer.


### INSTALLING INTERCEPTION (tricky):
- Navigate to the folder location of "install-interception.exe" in Windows File Explorer.
- Copy the address from the address bar.
- Open the start menu, and type in <kbd>C</kbd><kbd>M</kbd><kbd>D</kbd>. DO NOT hit "ENTER."
- Instead, <kbd>right click</kbd> on the command prompt item that appeared in your start menu, and <kbd>click</kbd> on "Run as administrator"
- Now inside the admin command prompt, type in "<kbd>c</kbd><kbd>d</kbd><kbd>[spacebar]</kbd>" and hit <kbd>CTRL</kbd> <kbd>V</kbd> to paste the explorer address. For me, I had to type in the following:
```cmd
cd C:\Users\Taran Baron\Downloads\Interception\command line installer
```
- Hit <kbd>ENTER</kbd>
- Now, type in the following line of text exactly as shown:
```
install-interception.exe /install
```
- ...and hit <kbd>ENTER</kbd>
- Once the program installs sucessfully, you still must restart your computer in order to complete the installation.

- (If you ever want to UNinstall interception, watch this): https://www.youtube.com/watch?v=Hn18vv--sFY

### USING INTERCEPT.EXE (Tutorial) -- (This is different from intercepTION!)
- Download Kamaz's intercept.exe zip from here:
- http://octopup.org/img/code/interception/intercept.zip
	(If it's no longer available from that location, I've already rehosted it in this folder.)
- Unzip intercept.zip to some location on your computer.
- Plug in your second keyboard and ensure that it is working normally.
- Double click on intercept.exe. It will open a command prompt thingy.
- Type <kbd>a</kbd> to add a key.
- On the SECONDARY keyboard, press the <kbd>Q</kbd> key once.
- You will be prompted with "Enter combo for this trigger, end with ESC."
- Carefully execute the following keystrokes (it doesn't matter which keyboard):

<kbd>F12 down</kbd>
<kbd>Q down</kbd>
<kbd>Q up</kbd>
<kbd>F12 up</kbd>
<kbd>ESC</kbd>

- Now press <kbd>Q</kbd> again to label the script
- Press <kbd>ENTER</kbd> to accept this label.
- Press <kbd>S</kbd> to save the filter, or <kbd>C</kbd> to cancel if you made a mistake.
- This has the effect of basically "wrapping" the keystroke inside of another keystroke.
- Now repeat the above steps, but using the keys <kbd>W</kbd>, <kbd>E</kbd>, and <kbd>R</kbd>.
- If you make a mistake, you can always just open the .ini file in a text editor and delete any bad entries.


### OPTIONAL: CREATING THE AUTOHOTKEY SCRIPT
- Download and install autohotkey if you don't have it:
- https://autohotkey.com/
- Right click on the desktop and select "New" > "AutoHotKey Script"
- Name the file "baby's first extra keyboard.ahk"
- Right click on the file and choose "Open with" > "Notepad". (Or, use your text editor of choice. Do not use Word.)
- In that file, there will already be a few lines of code. Beneath them, insert the following lines of code, up to the #if:
```
#SingleInstance force
#if (getKeyState("F12", "P"))
F12::return
q::msgbox, you pressed Q on the extra keyboard
w::msgbox, you pressed %A_thishotkey% on the extra keyboard
e::tooltip, you pressed %A_thishotkey% on the extra keyboard
r::SoundBeep, 1000, 500
#if
;Done with F12
```
- Now save the file. ("baby's first extra keyboard.ahk")
- Double click on the file to get it running.


### RECOMMENDED: USE ZAHUCZKY'S AUTOHOTKEY SCRIPT WITH PREMADE TYPESETTING FUNCTIONS AND BINDINGS
- Download and install Autohotkey as detailed above.
- Download "Typesetting_Keyboard_by_Zahuczky.ahk" from this repo.
- Run it.
- **KEEP IN MIND:**
- The macros inside this script **heavily** rely on already made and installed Aegisub scripts and hotkey bindings!
- More reading about dependencies, other key bindings can be found below
- For the usage of this Autohotkey script, reading and understanding this is **neccesary**.


### Key bindings in Zahuczky's "Typesetting_Keyboard_by_Zahuczky.ahk" script
**Bold** script name means it's available in [Dependency Control](https://github.com/TypesettingTools/DependencyControl), while colored means it's not, but it's linked.

- Q: Sets Perspective from clip (Relies on [perspective.moon](https://github.com/Alendt/Aegisub-Scripts/blob/master/perspective.moon) macro set to Ctrl+Q) {keycap done}
- Y: Turns line into vectors (Relies on [Stroke Panel](https://github.com/zerefxx/Aegisub-macros/releases/tag/vSaveOld) set to Alt+Y) (Y on QWERTZ, Z on QWERTY) {keycap done}
- B: Adds \blur0.8 (Relies on **HYDRA** set to Ctrl+G) {keycap done}
- V: Adds \bord4 (Relies on **HYDRA** set to Ctrl+G) {keycap done}
- N: Trim with Aegisub motion (Relies on **aegi-mo/trim** set to Alt+N) {keycap done}
- M: Open Aegisub motion (Relies on **aegi-mo/apply** set to Alt+M) {keycap done}
- H: Encode clip with subtitles and audio (Relies on petzku/**encode clip**/clip with subtitles set to Ctrl+Alt+H) {keycap done}
- J: Open Hyperdimensional relocator (Relies on **relocator** set to Ctrl+Alt+J) {keycap done}
- P: Open Position shifter (Relies on [Position Shifter](https://github.com/tophf/ijitsuki/blob/master/Position%20shifter.moon) set to Ctrl+P) {keycap done}
- S: Strip tags (Relies on Strip tags set to Ctrl+Alt+S) {keycap done}
- D: Open Shake It (Relies on **shake it** set to Ctrl+Alt+D) {keycap done}
- G: Gradient by character (Relies on **gradient by character** set ti Alt+G) {keycap done}
- F: Remove Gradient by character (Relies on **gradient by character** set ti Ctrl+Alt+F) {keycap done}
- T: Adds Shad Trick (Relies on **HYDRA** set to Ctrl+G) {keycap done}
- K: Apply karaoke effect without furigana with log's [karaOK](https://github.com/logarrhythmic/karaOK) library (Relies on karaOK set to Ctrl+Alt+K) {keycap done}
- Num 0: Opens Aegisub {TBD If already open, switch to that windows} {keycap done}
- Num 1: Navigates to Aegisub recent files in file menu {keycap done}
- Num 2: Opens Blender {TBD If already open, switch to that window} {keycap done}
- Num 3: Opens Mocha {TBD If already open, switch to that window} {keycap done}
- Num 4: Opens Illustrator {TBD If already open, switch to that window} {keycap done}
- Num 5: Opens Photoshop {TBD If already open, switch to that window} {keycap done}

TBD:
Font collector

![My layout](https://github.com/Zahuczky/2nd-typesetting-keyboard/blob/master/KEYCAPS/my_layout.png?raw=true)


### PUTTING IT ALL TOGETHER:

- Make sure that Intercept.exe is running, with the filters applied. (press Y to apply them. Do not close the window.)
- Open a blank text file and type "QWERTY" using your primary keyboard in it to ensure that it works.
- Now, type Q, W, E, or R on your secondary keyboard. Instead of text, you should recieve message boxes, tooltips, or a beep.
- Now that you have that working, you can restart intercept.exe, and (A)dd all the remaining keys, using the method described above.
- HOWEVER, that will be very slow. So instead, you can download and use Zahuczky's or Taran's files, "keyremap.ini"(Zahuczky's version contains the Hungarian `Í` key) and "Typesetting_Keyboard_by_Zahuczky.ahk"(Set up for typesetting) or "FULL_extra_keyboard.ahk"(blank) and customize them to your own computer.


- If you use Zahuczky's keyremap.ini, be sure to "find and replace" all instances of this line:
```
device=HID\VID_0C45&PID_8603&REV_0200&MI_00
```
or if you use Taran's keyremap.ini this:
```
device=HID\VID_046D&PID_C31C&REV_6400&MI_00
```
...with the device ID of your own secondary keyboard. (Again, you can get this info by (A)dding a filter in intercept.exe.)

- If you create your own keyremap.ini, you should find and replace all instances of `58,0,` (the scan code for F12) with `6E,0,` (the scan code for F23.) This is simply so that you do not make your F12 key unusable.
- Also, ensure that your AutoHotKey script is listening for F23 rather than F12, by modifying the code like so:
```
#if (getKeyState("F23", "P"))
F23::return

;;; put all your keys here ;;;

#if
;Done with F23
```




### ADDITIONAL RECOURCES:
> Taran's full repository with more stuff: 

> https://github.com/TaranVH/2nd-keyboard

> Kamaz's original post:

> http://orbiter-forum.com/showthread.php?t=30829

> geoffff's follow-up post:

> https://autohotkey.com/boards/viewtopic.php?p=61425&sid=c49c82a1247806ce92836a945aad4b37#p61425



