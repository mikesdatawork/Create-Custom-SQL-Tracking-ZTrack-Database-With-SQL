![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# Create Custom SQL Tracking [ZTrack] Database With SQL
**Post Date: November 20, 2015**        



## Contents    
- [About Process](##About-Process)  
- [SQL Logic](#SQL-Logic)  
- [Build Info](#Build-Info)  
- [Author](#Author)  
- [License](#License)       

## About-Process

<p>The ZTRACK database is my simple little tracking solution without having to incorporate any other database services, or associated SQL Features. Basically this is a custom Database that's managed with just a series of Agent Jobs, queries, triggers. If you're the kind of DBA that likes to write up your own kind of solution cause it's fast, reliable, and doesn't require a lot of effort then this is for you. Everything is contained without the ZTRACK Database so any objects you create (aside from triggers which mainly reside on the system tables), should be kept in this database.
Lets begin. First; create a database called ZTRACK. Nothing fancy. Use all the defaults, then run the following logic to create the tables. The first table of the ZTRACK database is called ABOUT_ZTRACK. This gives a basic description for everything you create. I'm prefixing the table names with "zt" as to avoid any name collision with reserved keywords. This might make queries alittle easier.</p>      


## SQL-Logic
```SQL
use ZTRACK;
set nocount on
 
create table ABOUT_ZTRACK
(
zt_id int identity(1,1) primary key not null
,   zt_object_type varchar(255)
,   zt_object_name varchar(255)
,   zt_object_logic varchar(max) default 'None'
,   zt_description varchar(max)
)
 
insert into about_ztrack
(
zt_object_type
,   zt_object_name
--, zt_object_logic
,   zt_description
)
values
(
'DATABASE'
,   'ZTRACK'
--,
,   'This Database is desiged to hold information about various system configurations, growth history, and performance history.' )
```
It's up to you to commit to creating a an entry and give it a description… Or… create a triggers under the SYSOBJECTS table, and create an entry automatically; then you can simply update the zt_description column later on if necessary. 


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)


  
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

