https://cliffle.com/blog/recode/

# Using the Keyboard
--> Dip Switches work as they did on WASD.

--> Console mode is active, but debug switched.  run `qmk console`
--> DEBUG MODE is active via L Shift + R Shift + 'd'

# Start by setting up qmk (mac) - https://docs.qmk.fm/newbs_getting_started
curl -fsSL https://install.qmk.fm | sh



qmk setup

If you used your own fork, 
❯ git remote add upstream git@github.com:qmk/qmk_firmware.git


# Visit https://cliffle.com/widget/recode/manual#_building_it_yourself
Concretely:

Install the QMK tools. If you haven’t worked with QMK before, follow their getting-started guide.

Add my fork to your QMK checkout with git remote add recode https://github.com/cbiffle/recode-qmk/

Checkout the recode branch: git checkout recode/recode

## Test Env
qmk compile -kb cbiffle/recodev2tkl -km default


## then
Build and flash appropriate image:

Tenkeyless (original) boards: qmk flash -kb cbiffle/recodev2tkl -km default

Universal (rev-C) boards:

In a tenkeyless keyboard: qmk flash -kb cbiffle/recode_revc -km tkl_ansi

In a full-size keyboard: qmk flash -kb cbiffle/recode_revc -km fullsize_ansi

At the end of the build, qmk will try to flash the image onto the keyboard. This requires you to put the keyboard into DFU mode. There are two ways to do this:

Unplug the keyboard, hold down the ESC key, and plug it in while still holding ESC.

If you have enabled the Fn key (dip switch 6 is ON), press Fn-ESC to reboot the keyboard without unplugging it.

Note that once you do this, your keyboard will stop being a keyboard until flashing is complete. You might want to have a backup on hand, just in case.i
