# FreeDMS
A structured way to organize your data in standardized folders. 
This makes project structures repeatable and machine-readable and makes exchanging with others simple.

## Motivation
Why does my TV find the videos, pics, and music on my computer? Because they are easy to find in the folders **_videos¸ _pictures, _music** which are located in my home directory. Then there are some APIs and stuff to retrieve it. But the principal idea is standardization. Everyone knows where to put his pictures.

When I'm organizing my documents in the **_documents** folder, I'm completely free to organize my stuff in any structure of folders I want. That's what I want to keep. But as anyone organizes his folders in a different way, it's difficult if not impossible for computers to analyze these different structures.
I for example like to organize my stuff in projects. Each folder might have several subfolders for subprojects or typical data. This way I'm building a quite fancy hierarchy of projects and subprojects. But once that done, I have to rebuild this project hierarchy again in my mail client, and in my financial software, maybe in my pictures folder and on my cellphone, ... keeping all this in sync is an everlasting source of inconsistency.

## Principle
The idea is to still use folders for organizing my projects (project folders) and to *add some standardized folders* to my project folders (on demand - just if they are needed).
Projects almost always have some administrative stuff, some financial issues, some legal issues, maybe some technical issues, and so on. These things should be placed always into the same subfolders of my project.

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

Each such folder might on its own have some standardized subfolders like

    _finance/_purchases
    _finance/_sales
    _finance/_insurances

or like

    _work/_preparations
    _work/_plan
    _work/_act
    _work/_check
    _work/_learnings

"When needed" means that these folders are not always there by default but they are added on demand.
The trick is to always add the same folders and to establish a universal structure.

## Advantages
  * I always know exactly where to place my documents, my tickets, my bills, my information, and documentation and I'll find them again in 20 years.
  * Any software like my mailclient i.e. can read my project structure as it is represented by the path to my project:
    **home/Projects/Family/Holidays/2022_USA_Trip/_communication**
  * Easy handling of permissions: My financial software might have just access to all the _finance folders and subfolders.
  * When sharing projects or parts of projects with others everyone immediately recognizes the same structures and they'll find their  way.

## An example
Imagine the process of __booking a flight__. Once I've booked my tickets, I often can download them as well as some legal documents and so on. I'm asked in the "save"-dialog where to save all the pdf files. There I can navigate to my "Travels"-folder or create a new folder like "2022_USA_Trip". That's exactly where I navigate inside my project hierarchy and create it respectively.

The filght-company might one day send tagged documents like:
* Bill.pdf (tagged with '_finance/_purchases') so it will find its way into the folder **_finance/_purchases**
* AGBs.pdf (tagged with _legal) will find its way into the (project-)folder **_legal**.
* Tickets.pdf (tagged with _work/_preparations)
* Infos.pdf (tagged with _information)
* : and so on.
When downloading my documents, my email-client asks me where to save the files. I browse to my holidays-folder and there it creates all the necessary folders if they do not already exist.

The point is, that the folders are always called "_finance" and not once "bills", next time "finances", "tickets", ...
Also when folders are created, permissions might be given to these folders according to a custom scheme. Like my financial software might belong to the group "_finance_rw". This group has access to all my "_finance" folders and each newly created folder "_finance" gives rights to read and write to the group "_finances_rw". So it will be automatically accessible for my financial software.

## Free to configure or standardized?
An open question is if the users should be able to configure the scheme according to their needs. This would be nice but it would destroy any attempts of standardization.
In case one goes for standardization, it would be important that the number of standard folders in one level stays small and not everyone adds some folders to the structure as they think it might be fancy. So there should not be additional folders like _IBM_finances, _GOOGLE_finances, ... because IBM thinks it would be better to structurize the _finances into _in, _out, _offers, and _bills and GOOGLE thinks it should be structured into _buy, _sell, _rent, _interests, ...
So there should be a primary structure of standard project folders that can be discussed but should be fixed once and then stay for quite a time. A first proposal for such a basic structure can be found in the file: [FreeDMS_structure.md](FreeDMS Structure.md)

## principal design rules
The first design rule for such a structure should always be: New users should find their way with as few as possible explanations.
A folder _finance is self-explanatory while a folder _exchange is not. Exchanging files is the principal idea of this concept. 
Hierarchical structures are always suffering from some inconsistencies. Like do _insurances belong to _finances or to _legal ? For this each folder might contain a read.me file that explains which things belong in this folder and which do not. For these things the right folder should be mentioned in the read.me-file.

The second design rule should be KISS.

The third design rule should be: Don't make or show empty folders. When browsing a folder, then empty folders inside this folder could simply not be shown. Even better they never got created, or deleted automatically when the last file inside of them has been removed. While in a dialog where the user wants to save a new file empty folders of the predefined structure could be shown in a semi-transparent way. So the user simply can drop his file into such a folder that doesn't yet exist or even might browse into a non-existing sub-sub-folder to drop his file there. The new folders are then created automatically on the fly.

Exemple: The user has just created a new project folder and now wants to drop a new file inside. It's a bill. So one day, when the whole project is already filled with plenty of files and the structure is already well established, they might place their file.pdf somewhere like: ./myProject/_finance/_bills/2022/Feb/file.pdf_
But at this moment there is just the project-folder ./myProject/ so when browsing into this folder the Filebrowser shows in a semi-transprent way all the yet non existing structural folders like _info, _admin, _communication, _finance, _legal, ..._ The user now proceeds into the _finance-folder_ and might drop his document there. Or they now find there semitransparent folders like _assurances, _invoices, _bills, ..._ and they might proceed to the _bills-folder_. There they might create the two folders _2022_ and _Feb_ and finally drop their document there. Now all these folders are created.
As for now, there is just one file in the project, the file browser when opening the ./myProject-folder doesn't show something like ./myProject/_finance_. Instead, it shows something like ./myProject/(_finance/_bills/2022/Feb/)file.pdf_. The (brackets) mean that the file is shown directly and just in its name, the file-path is shown additionally. Maybe the file-icon is surrounded by a folder-icon (or shown above a folder-icon). So we see immediately - this file is placed in at least one more folders, but for the moment we can access it directly with one click. 
As long as there are not more than 10 or maybe 15 files inside the ./myProject folder files are shown like this. In case there are more than 3 files placed somewhere inside the _finance-folder_ this folder might been shown. So the useres can maintain the file-hierarchy without having to hassle with browsing through a multitude of folders right from the beginning.

A next design priciple might be: Don't stop at folder-borders while browsing. Thinking of photos. People are used to oranize their fotos in folders like ./photos/2022/feb or ./photos/2022/feb-18-Birthday of Emily. It can be annoying when browsing through such structures, when there are just 2 photos inside such folders. But it would make sense to follow the structure as the folders also give kind of a taxonomy or history. So why not, when you reach the last photo in a folder and you want to proceed to the next image, just show the next Foldername as an image, change into this folder and show the images there.
So in the exemple above if the user is actually browsing inside the folder ./photos/2022/feb they might see the pics pic0123.jpg > pic0124.jpg > pic 0125.jpg which might be the last picture inside this folder. If the user now proceeds to the next image, instead of not proceeding or starting the same folder from the beginning, the browser might show a folder-picture with the heading "feb-18-Birthday of Emily" and as a next image the first picture of this folder. 
