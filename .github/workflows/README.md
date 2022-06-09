# Build custom vial firmware with Github Actions

I made this repo to keep my custom vial config and firmware, and to avoid having to set up a build 
environment on a local PC. It uses github actions to take the firmware in the 'custom-vial' folder, 
set up a containerized build environment, and build and output the firmware. If you create a tag, 
it will also attach that build to a release for easy access in the future. 

You could use this repo for any keyboard like this:

1. Clone or fork the repo
2. Create a folder for your keymap, and put it in the keymaps directory of the repo
3. Edit the env variables in the .gituhub/workflows/build-firmware.yml to reflect the keyboard that 
   you are building for and the name of your keymap - i.e update KEYBOARD to be the name of the target 
   keyboard and KEYMAP to be the name of the keymap folder you created in step 2
4. Push the repo to your fork and enable the workflow action. If you want to build/maintain multiple 
   keyboards then you can create multiple folders (step 2) and duplicate the github actions, updating 
   the variables as in step 3 to suit
