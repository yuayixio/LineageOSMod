# Bachelorthesis FX

Code for the Bachelorthesis at AIFB about mobile security in the OS LineageOS. Short manual on how to compile the system is on the button of the text-file.

Main Branch/Final form

The main branch is the code of the presentation and basically the final form of the source code. The changes are mainly about the Settings addition of the "Provide Fake Contacts" button.

____________________________________________________________________________
!!!
THE OTHER CHANGES TALKED ABOUT IN THE THESIS CAN BE FOUND IN THE OTHER BRANCHES. JUST LOOK UP THE README FILE!!

*  ModifyingTheUI branch: Modifying the UI Chapter
*  ProvidingFCPGallowed branch: Passing fake contacts when permission allowed, but caller is not Contacts application. Only the system's contacts application gains access to contacts database. Providing Fake Contacts Chapter Pt. 2
*  FakeContactsDefault branch: Simply passing fake contacts when Permission is deinied. --> Providing Fake Contacts Chapter Pt.1
*  Master branch: Modifying the Settings Chapter
!!!
____________________________________________________________________________

IN THIS BRANCH:

In this branch, the main changes were done in the "Settings Modification" Directory. Here, the new Setting-option including the check box was added to the interface and functionality was given. While adding the new entry, a String needed to be defined and the functionality was programmed, by saving the state of the Checkbox in the Settings.System class. This package might need an import if it's not already there!
Just include "import android.providers.Settings" in the code.

Additionally, the ContactsProviders2 class was edited, to be found in the "Providers" directory. Here, it is important to have the Settings imported as well and check the value of the checkbox, before the Fake contacts are passed. Since the Fake Contacts is only supposed to obe passed when the "Read Contacts" operation is allowed, we modified the ContactsProvider2.java class instead of the ContentProvider.java class.

_____________________________________________________________________________


Manual on how to compile the system:

- To start this work, the code name of the phone was searched (https://wiki.lineageos.org/devices/). In our case (Moto G), it was named falcon. Consider this for the next links, you need to choose the correct manual, suited for your phone. This decides which realease of LineageOS you should donwload as well as changes the shell commands, especially for the "Brunch" and "breakfast" commands.
- Then, the system was installed, this makes it easier to later build it yourself. (https://wiki.lineageos.org/devices/falcon/install)
- Afterwards, for the first time compiling, the general manual of the LineageOS website was used (https://wiki.lineageos.org/devices/falcon/build). 
- Here, if the breakfast or brunch part fails, you might need to use "theMuppets", which provide you with vendor specific code. (https://gist.github.com/fourkbomb/261ced58cd029c5f7742350aafdd9825)
- Then you need to flash the system on your phone, similar to the installation process. (I did it from recovery, which worked out fine)
- If you're finished with this whole process, you should have LineageOS on your phone as well as on your PC.
- To edit the system, there are different options:
  
    1. Modify the code in your local directory over the text editor. This is the fastest way of doing so, but there is no auto-fill or mistake detection (semicolons or missing brackets). Anyway, if you want to do small changes and exactly know which classes you need to edit, this is the most conveniant way.
    2. Using an IDE (Eclipse or Android Studio). This contains the disadvantages mentioned in the first chapter, but is slower and not optimized for mobile system code development, but rather on app development. Thus, not all faults (e.g. missing references) are actual errors when it comes to compiling. Also, since the whole code is huge, it can take a while to compile. Very good for searching the code tho. 
    3. Using Git. (Github, Gitlab etc.) This is the most professional way, since the change history is saved and everything can be tracked. Anyway, if you are not familiar with git, it takes a little time to work yourself into it. As soon as you are familiar with it, it will definetly help during your modifications! 

- Once the changes are made and, in the case of Git, downloaded, you can just repeat the steps from the build process to recompile your system by:
    
    1. go back to the correct directory ("cd ~/android/linaege")
    2. run the envsetup script ("source build/envsetup.sh")
    3. build the system again (brunch DEVICENAME)

- Since there was cache saved, the second time finishes way faster. Then you need to flash your phone again and you have your modified system on your device!