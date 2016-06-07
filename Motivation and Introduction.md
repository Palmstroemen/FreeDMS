# FreeDMS
A structured way to organize your data in standardized folders. 
This makes project structures repeatable and machine readable and makes exchanging with others simple.

## Motivation
Why does my TV find the videos, pics and music on my computer? Because they are easy to find in the folders _videos¸ _pictures, _music which are located in my home directory. Then there are some APIs and stuff to retrieve it. But the principal idea is standaridzation. Everyone knows where to put his pictures.

Now when organizing my documents in the ¸_documents¸ folder, I'm completely free to organize my stuff in any structure of folders as I want. That's what I want to keep. But as anyone organizes his folders in a different way, it's difficult if not impossible for computers to analyze this different structures.
I.E. I like to organize my stuff in projects. Building a quite fancy hierarchy of projects and subprojects. But once that done, I have to rebuild this project hierarchy again in my mail client, and in my financial software again, ... keeping all this in sync is an everlasting source of inconsistency.

## Principle
Now the idea is to add some standardized folders to my projectfolders (on demand - just if they are needed).
Like projects almost always have some administrational stuff, some financial issues, some legal issues, maybe some technical issues.

So i'd like to add folders like these to my projects when needed:

    _admin
    
    _information
    
    _communication
    
    _finance
    _legal
    _tech
    _work
    _documentation¸
_(The leading Underscore marks them as my special freeDMS-folders and keeps them all together if there are other folders of subprojects in my hierarchy)_

Each folder might have some standardized subfolders like
_finance/_purchases
_finance/_sales
_finance/_AppData

or like
_work/_preparations
_work/_plan
_work/_act
_work/_check
_work/_learnings
_work/_AppData

"When needed" means, that these folders are not always there by default, but they are added on demand.
The trick is to always add the same folders and to establish a universal structure.

## Advantages

  * any software like my mailclient i.e. can read my project structure as it is represented by the path to my project:
    home/Projects/Family/Holidays/2015_USA_Trip/_communication
    my financial software might have just access to all the _finance folders and subfolders.
  * Also I know exactly where to place my documents, my tickets, my bills, my informations and documentation and I'll finde them again in 20 years.
  * When sharing projects or parts of projects with others everyone immediately recognizes the same structures and finds his way easily.

## An exemple
Imagine the process of __booking a flight__. The filght-company might send tagged mails like:
Bill.pdf (tagged with _finance/_purchases) will find its way into the folder _finance/_purchases
AGBs.pdf (tagged with _legal) will find its way into the (project-)folder _legal.
Tickets.pdf (tagged with _work/_preparations)
Infos.pdf (tagged with _information)
: and so on.
When downloading my documents, my email-client asks me where to save the files. I browse to my holidays-folder and there it creates all the necessary folders if they do not already exist.

The point is, that the folders are always called like "_finance" and not once "bills", next time "finances", "tickets", ...

## technically speaking
This shall be realized by scripts that provide an API for the most common operating systems. It should be a lightweight layer above the operating system that anyone can easily add to his OS. The standard folders shall be localized later. So _legals might appear as "Rechtliches" in german and as "Legal affairs" in english. The user might even be able to call folders his own way. 

Once these scripts exist, programs can start to use this structures.
  * A file-browser could show such folders that do not exist yet in a semi-transparent way or with special icons. If you place a file in such a non existing folder, this folder is created. This way your projects are not filled up with a bunch of empty folders by default. 
  * The filebrowser also might (if I like that) show all my documents directly without the proposed structure of folders. He kind of "hides" the folders and just shows additional icons on my files that indicate if they are in _finance/_sales or in _legal. 
  * A mail-client could read out tags attached to documents and send attachments to the appropriate folders or place mails into the _communications folder.
  * A financial software could collect all the data from the _finance folders all over the project.
  * Photos could be placed into a _documentation/_images folder.

## not too much
It's important that the number of standard folders in one level stays small and not everyone adds some folders to the structure as they think it might be fancy. So there should not be additional folders like _IBM_finances, _GOOGLE_finances, ... because IBM thinks it would be better to structureize the _finances into _in, _out, _offers and _bills and GOOGLE thinks it should be structured into _buy, _sell, _rent, _interests, ...
So there is a primary structure of standard project folders that can be discussed but should be fixed once and then stay for quite a time. This basic structure can be found in the file: FreeDMS_template
