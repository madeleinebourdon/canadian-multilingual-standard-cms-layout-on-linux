# Canadian Multilingual Standard Layout on Linux
I was annoyed there was no **Canadian Multilingual Standard** (CMS) layout on Linux, so I made my own. 

It seems CMS was exclusive to Windows. Mac OS has a variant of it, but it's not exactly the same.

I made this with **Fedora** and **SteamOS** in mind, but it seems that the keyboard system is the same for most Linux distros. **As long as XKB (X Keyboard Extension) works on your Linux, this layout should work for you.**



# Installation
- Copy the `cms` file from this repo into your folder `/usr/share/X11/xkb/symbols/` (you will need root privileges)
- Edit your `evdev.xml` (in `/usr/share/X11/xkb/rules/evdev.xml`) and add inside a reference to this file, along the references that already exist
  - Example :
    - ```
      <layout>
        <configItem>
          <name>cms</name>
          <shortDescription>CMS</shortDescription>
          <description>Canadian Multilingual Standard (Windows, ANSI)</description>
        </configItem>
      </layout>
      ```
- Reload your Linux's system or log out / log in to reload your updated `evdev.xml`
- Now, you're able to choose CMS in your Linux's layout options.
  - Go to `System Settings` > `Input Devices` > `Keyboards` > `Layouts`
  - Click `Add`
  - Select `Canadian Multilingual Standard (Windows, ANSI)` in the first column
  - Click `OK`
  - Your new keyboard layout is ready!

# Notes
- As the name suggests, I replicated the feel I had on Windows with my ANSI (american) keyboard. I have not tested my layout with an ISO keyboard.
- Also, I had issues implementing the fourth layer of the CMS design. It seems Linux does not handle it as well as Windows did. As a result, this design might have a few missing symbols on the fourth layer. I never used this layer anyway, but I'd prefer to mention it.
- Finally: if you do not nuke your `evdev.xml` by mistake (and even then, I'm pretty sure there's a fix), the worst that can happen is to have Linux default back to another output it knows. This file is just a list of characters that are triggered when each specific key is fired.

