# Bachelorthesis FX

Code for the Bachelorthesis at AIFB about mobile security in the OS LineageOS.

This branch is representing the second part of the "Provide Fake Contact" chapter of the thesis. Here, the goal was to 

ONLY PASS CONTACTS TO THE SYSTEM OWN CONTACTS PERMISSION, BUT NOT TO THIRD PARTY APPS.

That's why the ContactsProvider2 was edited with a comparison, whether the caller is the Contacts application or not. This is realized by  using the "callingPckg" value, which indicates which package is calling, and check whether the "android.com.contacts" package is calling or not.