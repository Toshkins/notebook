
setup
installed the PnS environment created by claude
to use the open-in-xcode.command had to remove the download flag using `xattr -dr com.apple.quaratine mac`

    bash mac/open-in-xcode.command
to open the project in Xcode then cmd-B to build all. This next command builds the test renderer

    cmake --build build-xcode --config Debug --target test_dsp host_sim render

then you can run the test code:

    ctest --test-dir build-xcode -C Debug
 Which should give an output like this:
 

    roshanwijetunge@Macmini pns-effects % ctest --test-dir build-xcode -C DebugTest project /Users/roshanwijetunge/dev/pns-effects/build-xcode
    Start 1: dsp_blocks
    1/8 Test #1: dsp_blocks ....................... Passed  0.03 sec
    Start 2: render_tone
    2/8 Test #2: render_tone ...................... Passed  0.01 sec
    Start 3: render_gain
    3/8 Test #3: render_gain ...................... Passed  0.02 sec
    Start 4: render_drive
    4/8 Test #4: render_drive ..................... Passed  0.02 sec
    Start 5: render_echo
    5/8 Test #5: render_echo ...................... Passed  0.05 sec
    Start 6: effect_drive
    6/8 Test #6: effect_drive ..................... Passed  0.06 sec
    Start 7: effect_echo
    7/8 Test #7: effect_echo ...................... Passed  0.12 sec
    Start 8: effect_gain
    8/8 Test #8: effect_gain ...................... Passed  0.01 sec
    100% tests passed out of 8
    Total Test time (real) = 0.33 sec


I then created GitHub remote repos pns-effects and  notebook (where this markdown goes), initialised git locally:

    git config --global user.name "Toshkins"
    git config --global user.email "rwijet@googlemail.com"
    gh auth login
    git init && git add . && git commit -m "Initial import"
    git remote add origin https://github.com/Toshkins/pns-effects.git
    git branch -M main
    git push -u origin main


> Written with [StackEdit](https://stackedit.io/).
