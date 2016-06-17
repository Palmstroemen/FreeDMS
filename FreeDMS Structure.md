# FreeDMS Structure
a first proposal for a structure.

AnyFolder

    _FeeDMS				(hidden?) contains dadministrative data for FreeDMS, DB_history, FreeDMS Version, SVN, ...
    	Context.file	a file that might contain the path for various users
    _admin              
        DB_stakeholder	Accessrights (roles, groups, also "world", "projectmembers", ...) maybe in _FreeDMS
        DB_contacts		Database of contacts - maybe in _FreeDMS
    _inbox				everything that's not filed yet.
    _info				general infos that are necessary for the project 
    _communication      
  	    _drafts
    	_up 			communication to superproject
  	    _intern 		communication within the project on the same level
  	    _extern 		communication with externals (Web, public affairs, ...)
  	    _down 		    general communication to all subprojects (for singular communications use folder _up in subproject)
  	    _to 			communication to other projects
    _finance
  	    _drafts			
  	    _offersIN		received offers
  	    _offersOUT		offers from the project to others
  	    _billsIN		purchases
  	    _billsOUT		sales
    _legal
  	    _drafts			
        _laws			general terms and conditions, laws, standards
  	    _contracts		LOIs, NDAs, ...
  	    _cases			complaints, court files, law suits, ...
    _tech
  	    _downloads
  	    _techinfo		plans, scetches, datasheets, ...
        _programs		programs needed, programsettings, ...
    _work
  	    _plan			plans, Todo-lists, protocols of meetings ...
  	    _preparation    everything I need to do it.
  	    _do			    timesheets, intermediate data …
  	    _result			results
  	    _check		    evaluations, analysis, quality assurance, 
  	    _learnings        
  	_documentation
  	    _media		    images, videos, ...
  	    _documents      documentation, reports, ...
  	    _web            things to be published

Additionally every main folder contains an hidden folder _appdata. 
Applications may deposit their (for the user not readable) data like settings, binary files, ...

It's all about a good overview *for the user*. 
An application has no troubles to step deeper into a path by two additional folders.
  ProjectA/ProjectAa/_finance/_appdata/AppXY/Configurations.xml
