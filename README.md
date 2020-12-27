# Bachelorthesis FX

Code for the Bachelorthesis at AIFB about mobile security in the OS LineageOS.

The First approach of providing fake contacts, by simply passing fake contacts whenever the Read Contacts Permission is demanded and the PG for this app isn't set on "Allowed".

For that, just the *ContentProvider.java* class is modified. After checking if the permission is not granted through the Privacy Guard 

```java"permission" != AppOpsManager.MODE_ALLOWED
```

the fake contact is sent by pre-defining the contact details. Here, it is first checked whether the caller's query included a "projection", which is a enumeration of requested columns/contact details. Then, the faked contact information is put into a "Matrix Cursor" and finally passed back to the caller.
