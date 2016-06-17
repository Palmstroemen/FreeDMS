# FreeDMS
A structured way to organize your data in standardized folders. 
This makes project structures repeatable and machine readable and makes exchanging with others simple.

## Motivation
Why does my TV find the videos, pics and music on my computer? Because they are easy to find in the folders **_videos¸ _pictures, _music** which are located in my home directory. Then there are some APIs and stuff to retrieve it. But the principal idea is standaridzation. Everyone knows where to put his pictures.

When I'm organizing my documents in the **_documents** folder, I'm completely free to organize my stuff in any structure of folders as I want. That's what I want to keep. But as anyone organizes his folders in a different way, it's difficult if not impossible for computers to analyze this different structures.
I for exemple like to organize my stuff in projects. Each folder might have several subfolders for subprojects or typical data. This way I'm building a quite fancy hierarchy of projects and subprojects. But once that done, I have to rebuild this project hierarchy again in my mail client, and in my financial software, maybe in my pictures folder and on my cellphone, ... keeping all this in sync is an everlasting source of inconsistency.

## Principle
The idea is to still use folders for organizing my projects (projectfolders) and to *add some standardized folders* to my projectfolders (on demand - just if they are needed).
Projects almost always have some administrational stuff, some financial issues, some legal issues, maybe some technical issues and so on. These things should be placed always into the same subfolders of my project.

So i'd like to add folders like these to my projects when needed:

    _admin
    _information
    _communication
    _finance
    _legal
    _tech
    _work
    _documentation
    
_(The leading Underscore marks these folers as my special freeDMS-folders and keeps them all together if there are other folders of subprojects in my hierarchy)_

Each such folder might on his own have some standardized subfolders like

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
  * I always know exactly where to place my documents, my tickets, my bills, my informations and documentation and I'll finde them again in 20 years.
  * Any software like my mailclient i.e. can read my project structure as it is represented by the path to my project:
    **home/Projects/Family/Holidays/2015_USA_Trip/_communication**
  * Easy handling of permissions: My financial software might have just access to all the _finance folders and subfolders.
  * When sharing projects or parts of projects with others everyone immediately recognizes the same structures and finds his way.

## An exemple
Imagine the process of __booking a flight__. Once I've booked my tickets, I often can download them as well as some legal documents and so on. I'm asked in the "save"-dialog where to save all the pdf-files. There I can navigate to my "Travels"-folder or create a new folder like "2015_USA_Trip". That's exactly where I navigate inside my projects hierarchy and create it respecively.

The filght-company might one day send tagged documents like:
* Bill.pdf (tagged with '_finance/_purchases') so it will find its way into the folder **_finance/_purchases**
* AGBs.pdf (tagged with _legal) will find its way into the (project-)folder **_legal**.
* Tickets.pdf (tagged with _work/_preparations)
* Infos.pdf (tagged with _information)
* : and so on.
When downloading my documents, my email-client asks me where to save the files. I browse to my holidays-folder and there it creates all the necessary folders if they do not already exist.

The point is, that the folders are always called like "_finance" and not once "bills", next time "finances", "tickets", ...
Also when folders are created, permissions might be given to these folders according to a custom scheme. Like my financial software might belong to a group "_finance_rw". This group has access to all my "_finance" folders and each newly created folder "_finance" gives rights for reading and writing to the group "_finances_rw". So it will be automatically accessible for my financial software.

## not too much
It's important that the number of standard folders in one level stays small and not everyone adds some folders to the structure as they think it might be fancy. So there should not be additional folders like _IBM_finances, _GOOGLE_finances, ... because IBM thinks it would be better to structureize the _finances into _in, _out, _offers and _bills and GOOGLE thinks it should be structured into _buy, _sell, _rent, _interests, ...
So there is a primary structure of standard project folders that can be discussed but should be fixed once and then stay for quite a time. This basic structure can be found in the file: FreeDMS_structure
