<sup>[ en | [ru](https://github.com/yozhic/goldendict-macos-builds/blob/main/README_RU.md) ]</sup>  

# goldendict-macos-builds

Unofficial third-party builds of GoldenDict for macOS

Based on Qt 5.14.2 (Clang 11.0, x86_64) with QtWebKit 5.212.0 Alpha 4  
Tested on Mojave, Big Sur, Monterey, Ventura  

> [!IMPORTANT]  
> Provided "as is" with no warranty of any kind.  


## Overview

The `master` version is a macOS build of the (hopefully) most up-to-date version of [goldendict-master](https://github.com/goldendict/goldendict), without any additions or modifications.  

The `mac-adapted` version is an [attempt](https://github.com/yozhic/goldendict/tree/mac-adapted) to make GoldenDict look more presentable on newer macOS systems. It comes with an updated set of scalable icons and includes three additional display styles whose look and feel aims to match that of the OS itself. In all other respects it is exactly the same as the plain unaltered `master` version.  

To take full advantage of the UI improvements the `mac-adapted` version has to offer, navigate to _Preferences_ → _Interface_, click Display style and pick one of the three styles that were specifically crafted with macOS in mind:  

- macOS Light
- macOS Dark
- macOS Dark Deep


## Post-install

The steps below are required for certain features to function properly. It is highly recommended that you follow these steps every time you install or update GoldenDict:  

1.	Click the  Apple menu and select _System Preferences_ from the drop-down list.
2.	Under _Security & Privacy_, click the _Privacy_ tab and then _Accessibility_.
3.	Click the 🔒 lock icon at the bottom of the dialog to make changes.
4.	Scroll through the list of apps to make sure GoldenDict.app is _not_ on the list. If it is, remove it using the ➖ (_Delete_) button.
5.	Add GoldenDict.app to the list. There are two ways to do that: you can either drag and drop GoldenDict.app directly into the pane, or you can click the ➕ (_Add_) button, select GoldenDict.app and click _Open_.
6.	Enable the checkbox next to GoldenDict.app.


## Known issues

<dl>
  <dt>Command+C not working</dt>
    <dd>It is not uncommon for GoldenDict to interfere with your using <kbd>Command</kbd>+<kbd>C</kbd> (<i>Copy</i>) in other applications, so if you find that <kbd>Command</kbd>+<kbd>C</kbd> is not working for copying items, make sure to first try the steps outlined above under <i>Post-install</i>. If the problem persists, navigate to <i>Preferences</i> → <i>Hotkeys</i> and set the hotkey under <i>'Use the following hotkey to translate a word from clipboard'</i> to something other than the default <kbd>Command</kbd>+<kbd>C</kbd>+<kbd>C</kbd>.</dd>
  <dt>Scan Popup not working as it should</dt>
    <dd>This functionality seems to be largely broken on newer versions of macOS. The steps outlined under <i>Post-install</i> might help somewhat, but if they don't, just make sure the 'magic wand' button is not pressed, or indeed disable it completely by un-checking everything under <i>Preferences</i> → <i>Scan Popup</i>.</dd>
</dl>


## Download

You can get the latest release from the [Releases](https://github.com/yozhic/goldendict-macos-builds/releases) page.  


## Compare versions

![COMPARE LIGHT](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_LIGHT.png)  

![COMPARE DARK](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK.png)  

![COMPARE DARK DEEP](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK_DEEP.png)  

![COMPARE PREFS](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_PREFS.png)  

