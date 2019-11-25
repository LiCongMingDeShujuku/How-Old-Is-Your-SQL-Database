![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 你的数据库存在多长时间
#### Find How Old The SQL Database Is
**发布-日期: 2015年3月16日 (评论)**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
这里有一些快速的SQL逻辑显示数据库的存在时间。当然，你可以查询创建日期，但是这些逻辑语言将像你展示一个关于它已经存在多长时间的报告。


## English
Here’s some quick SQL Logic to show you how long a database has been around. Sure; you can check the create_date, but this will show you a report on how long it’s been.

---
## Logic
```SQL
select
    'database'          = sd.name
,   'created on'        = sd.create_date
,   'human readable'    = 
                            + cast(datediff(second, sd.create_date, getdate()) / 60 / 60 / 24 / 30 / 12 as nvarchar(50)) + ' years, '
                            + cast(datediff(second, sd.create_date, getdate()) / 60 / 60 / 24 / 30 % 12 as nvarchar(50)) + ' months, '
                            + cast(datediff(second, sd.create_date, getdate()) / 60 / 60 / 24 % 30 as nvarchar(50)) + ' days, '
                            + cast(datediff(second, sd.create_date, getdate()) / 60 / 60 % 24 as nvarchar(50)) + ' hours, '
                            + cast(datediff(second, sd.create_date, getdate()) / 60 % 60 as nvarchar(50)) + ' minutes '
                            + cast(datediff(second, sd.create_date, getdate()) % 60 as nvarchar(50)) + ' seconds '
from
    sys.databases sd
where
    sd.database_id > 4
order by
    sd.create_date desc


```



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

