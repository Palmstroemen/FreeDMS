# FreeDMS - Technical intro

FreeDMS shall be realized by scripts for the most common operating systems. It should be a lightweight layer above the operating system that anyone can easily add to his OS. The standard folders shall be localized later. So _legals might appear as "Rechtliches" in german and as "Legal affairs" in english. The user might even be able to call folders his own way. 


## A future vision:

Once these scripts exist, programs can start to use this structures.
  * A file-browser could show such folders that do not exist yet in a semi-transparent way or with special icons. If you place a file in such a non existing folder, this folder is created. This way your projects are not filled up with a bunch of empty folders by default. 
  * The filebrowser also might (if I like that) show all my documents directly without the proposed structure of folders. He kind of "hides" the folders and just shows additional icons on my files that indicate if they are in _finance/_sales or in _legal. 
  * A mail-client could read out tags attached to documents and send attachments to the appropriate folders or place mails into the _communications folder.
  * A financial software could collect all the data from the _finance folders all over the project.
  * Photos could be placed into a _documentation/_images folder.


## Terminology:
  * **Directories**              are all ordinary directories in the system
  * **freeDMS-directories**      are all directories that have been turned into freeDMS-projects.
  * **folders**                  are all subdirectories that can be added by freeDMS. Such as _finance, _tech, ...


## A first pragmatic approach:

As no other programs do support freeDMS in the beginning, there is another approach to make the system easy to use.
Once a directory has been turned into a freeDMS-project, there are some apps inside this directory:
  * CREATE NEW SUBPROJECT      to turn another directory into a project
  * ADD FOLDERS HERE           to add all Folders of the next level
  * (REMOVE EMPTY FOLDERS)     (toggles with ADD ALL FOLDERS HERE) to remove empty folders again.

This allows to easily organize existing projects and to turn them into freeDMS-projects.
The process is:
  1. CREATE NEW SUBPROJECT     wether by adding a new subdirectory or by turning an existing directory into a freeDMS-project.
  2. Navigate to this directory and ADD ALL FOLDERS HERE
  3. Move your data into these new directories. Follow the strategy not to hide your data in the deepest sub-folders.
     Put your files in the first level folders first. If there are too much files and it's getting crowded there, 
     add next level of folders and organize your files there. Think of these folders as proposals.
  4. Once you're done, REMOVE EMPTY FOLDERS again to just keep the folders you need.
     This cycle of ADDING and REMOVING you can repeat as often as you like. Existing files will never be overwritten.
     
There is also a folder **_tools** inside the folder **_admin** with further apps to manage the freeDMS-project. 
These apps allow for:
  *  SHOW ALL FOLDERS           To add all freeDMS-Folders up to the deepest hierarchy.
  *  REMOVE EMPTY FOLDERS       Functionally identical to the Button outside. (technically not)
  *  MANAGE TEAM                Add team members to the project and manage their accessrights. (Not implemented yet)
  *  RENAME THIS PROJECT        As some links might have to be corrected on renaming. (Not neccessary and implemented yet)
  *  ARCIVE THIS PROJECT        Copy some folders into the master Project and ZIP the folder. (Not implemented yet)


## Apps:
All these apps are simple .desktop-files. These are very small files that call a script.
There are some fancy and tricky things about these app.desktop-files a developer should know.
See: [tech App-files.md](/Texts/forDeveloppers/tech App-files.md)
