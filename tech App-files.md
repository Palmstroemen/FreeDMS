# Apps:
All these apps are simple .desktop-files. These are very small files that call a script.
There are some fancy and tricky things about these app.desktop-files a developer should know.

## What is an app.desktop-file?
A file with the extension .desktop and i.e. the following contents:
   [Desktop Entry]
   Encoding=UTF-8
   Version=1.0
   Type = Application
   Comment = "Add freeDMS Folders"
   Terminal = false
   Name = 1 ADD FOLDERS HERE
   Icon = /usr/share/icons/Humanity/actions/48/add.svg
   Exec = __Add_All_Folders -f %k

## Where from does the app call the script?
To tell the script, where the app-file is located inside the directory-tree the recent path to the .desktop-file is added to the call as parameter: 
i.e. execute addDMSfolders -f %k. -f is an option and %k is the current path including the filename. 
i.e. "/home/username/projects/subproject/ADD FOLDERS HERE.desktop"
This path sometimes might be different for the same principal functionality. (i.e. REMOVE EMPTY FOLDERS)
To distinguish these cases, different options are used.
   -f     if called from inside a folder.
   -a     if called from _tools inside the _admin folder.
   -p     if the path directly shall be used. (typically by a direct call from the terminal)
i.e. to find the way to the according freeDMS-project path:
   -f /home/username/projects/subproject/_finance/ADD FOLDERS HERE.desktop ... the last 2 entries need to be removed to get:
      /home/username/projects/subproject
   -a /home/username/projects/subproject/_admin/_tools/REMOVE EMPTY FOLDERS.desktop ... the last 3 entries must be removed.
   -p /home/username/projects/subproject ... nothing needs to be removed.

## How to turn an ordinary file into an .desktop-file?
  1. Check and doublecheck if all the properties are set as you want them. 
  2. Change the filename to something.desktop
  3. Give it executable-rights.

The name of an app is NOT the name of the .desktop-file!
This is most confusing during development. You may call your file 'myApp.desktop'. But the app has an name-property that will be shown as name of the app in the filebrowser. So if you set the name-property to 'XXX' then your app will be shown as 'XXX' to copy or delet the app-file you must use the original filename 'myApp.desktop'.

## Not all properties are easy to change once the file has been turned into a .desktop-file.
Some properties can be changed for a .desktop-file by using right mouseclick - properties.
  * Icon
  * Name
  * Ecec
  * Description
  * Comment
can be changed.
But i.e. the 'Terminal' property can't be changed.
For this there are the "Master" and "Debug" files to create apps with terminal and without terminal.
