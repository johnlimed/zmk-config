# My layout
```
Default layer
// ------------------------------------------------------------------------------------------
// | ESC |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  0  |  -  |  =  |   BKSP   |
// | TAB  |  Q  |  W  |  E  |  R  |  T  |  Y  |  U  |  I  |  O  |  P  |  [  |  ]   |   |    |
// | MO 1  |  A  |  S  |  D  |  F  |  G  |  H  |  J  |  K  |  L  |  ;  |  '  |     ENTER    |
// |  SHIFT    |  Z  |  X  |  C  |  V  |  B  |  N  |  M  |  ,  |  .  | /   |      SHIFT     |
// |  CTL  |  WIN  |  ALT  |            SPACE              | LEFT |   UP   |  DOWN  | RIGHT |
// ------------------------------------------------------------------------------------------

Raise layer
// ------------------------------------------------------------------------------------------
// | `  | F1 | F2 |  F3  |  F4  |  F5  |  F6  |  F7  |  F8  |  F9  | F10 | F11 | F12 | DEL  |
// |  CAPS | BT0 | BT1 | BT2 | BT3 | BT4 |     |     |     |     |     |     |     | BT CLR |
// |        |     |     |    |    |    | LEFT | UP | DOWN | RIGHT |     |     |             |
// |           |     |     |     |     |     |     |     |     |     |     |      MO3       |
// |       |       |       |                               | HOME | PG UP | PG DOWN |  END  |
// ------------------------------------------------------------------------------------------

Mac layer
// ------------------------------------------------------------------------------------------
// |     |     |     |     |     |     |     |     |     |     |     |     |     |          |
// |       |     |     |     |     |     |     |     |     |     |     |     |     |        |
// |        |     |     |     |     |     |     |     |     |     |     |     |             |
// |           |     |     |     |     |     |     |     |     |     |     |                |
// |       |  WIN  |  ALT  |                               |      |        |        |       |
// ------------------------------------------------------------------------------------------

Layers layer
// ------------------------------------------------------------------------------------------
// |   | TO 0 | MO 1 | TOG 2 |   |     |      |      |      |      |   |   |   | BOOTLOADER |
// |       |     |     |     |     |     |     |     |     |     |     |     |     |        |
// |        |     |     |     |     |     |     |     |     |     |     |     |             |
// |           |     |     |     |     |     |     |     |     |     |     |                |
// |       |       |       |                               |      |        |        |       |
// ------------------------------------------------------------------------------------------
```

# zmk-config
This is the ZMK-Config repo for the Polarity works BT60 keyboard, with this you can customise your layout and keymap to suit your exact needs.
We have provided base keymaps for the following layouts on the soldered version: ANSI, ISO, Split backspace and right shift, Tsangan and all 1u bottom rows. These can be accessed by choosing the appropriate branch. The hotswap version has one fork which already includes support for split backspace however it is not bound to anything useful thus you will need to fork and customise to your taste

# Customisation
In order to change the keymap to meet your needs, you will need a GitHub account. Click the "fork" button in the top right to create your own version of the repo, then use the drop down menu to select the branch with your layout.
The keymap information is contained entirely within the file bt60.keymap. Download this file to your computer and open it in a text editor such as Atom or notepad++ then you can open and edit it. The full list of ZMK keycodes can be found [here](https://zmkfirmware.dev/docs/codes/keyboard-keypad/).
After editing the keymap file upload it to the original folder using the "Add file" dialog in GitHub, then click on "Actions" and wait for the build process to complete (The orange dot will go to either a red X or green tick). If your firmware doesn't compile you most likely made a mistake with the keys, double check the .keymap file and try again.

# Compilation and downloading
 If you have made any errors in the keymap the compilation will fail and there will be a red X in the actions dialog. Click on it and it will tell you where the problem is.
 If the build completes with no errors you will be able to find the firmware in the "Artifacts" section of the last action.
 Put the keyboard into bootloader (Either double tap the hardware reset button or use the behaviour, typically fn + enter) and drag and drop the .uf2 file onto the usb drive that shows up

 # More advanced
 If you want to exercise greater control over your BT60 and have a unique layout implemented you will need to change the matrix transform. The following diagram displays which keys connect to which row and column pins. Note that everything is zero indexed in the matrix transform
 	![alt text](rowcolmap.png)
  The matrix transform can be found in bt60.dts, more information on how to do the matrix transforms can be found in the official ZMK documentation [here](https://zmkfirmware.dev/docs/development/new-shield#optional-matrix-transform)
  We're always willing to accept pull requests if you've developed your own layouts :)
