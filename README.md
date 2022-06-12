# Build custom vial firmware with Github Actions

I made this repo to keep my custom vial config and firmware, and to avoid having to set up a build 
environment on a local PC. It uses github actions to take the firmware in the 'keyboards' folder, 
set up a containerized build environment, and build and output the firmware. If you create a tag, 
it will also attach that build to a release for easy access in the future. 

You could use this repo for any keyboard like this:

1. Clone or fork the repo
2. Create a folder for your keyboard/keymap, and put it in the correct directory - as it would be in QMK. 
   For example, my custom nibble firmware goes into 
   `./keyboards/nullbitsco/nibble/keymaps/custom-vial` - you only need to add the keymap, if it builds
   on default or already existing firmware. **NB: If your keyboard/vendor has a shared directory for 
   common code for multiple keyboards, you will need to create that folder and add a .gitkeep file to
   it (see my nibble keymap, in this repo, as an example of this).
3. Optionally, if for some reason you don't want to use the Vial QMK fork, you can also update the 
   QMK_REPO and QMK_BRANCH variables to set which repository and branch you want to use for your 
   QMK clone. You should try Vial though - it's [easy to use](https://get.vial.today) and it [rocks](https://vial.rocks)
4. Push the repo to your fork and enable the workflow action. All the keyboards that are present in the folder will be copied and built

Leave an issue if something doesn't work. 

If you're interested in how it works, just look at the workflow - it uses git's sparse-checkout 
and a bit of sed/awk magic to work out which keyboards to check out and only checks out those
few keyboards that are relevant for the keymaps in the repo - that way you don't end up
building every keyboard going, and you don't have to specifically set out which keyboards/keymaps
you want building 
