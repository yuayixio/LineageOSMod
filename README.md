# Bachelorthesis FX

Code for the Bachelorthesis at AIFB about mobile security in the OS LineageOS.

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


Here, the main changes were done in the "Settings Modification" Directory. Here, the new Setting-option including the check box was added to the interface and functionality was given. While adding the new entry, a String needed to be defined and the functionality was programmed, by saving the state of the Checkbox in the Settings.System class. This package might need an import if it's not already there!
Just include "import android.providers.Settings" in the code.

Additionally, the ContactsProviders2 class was edited, to be found in the "Providers" directory. Here, it is important to have the Settings imported as well and check the value of the checkbox, before the Fake contacts are passed. Since the Fake Contacts is only supposed to obe passed when the "Read Contacts" operation is allowed, we modified the ContactsProvider2.java class instead of the ContentProvider.java class.