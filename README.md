# Lahman travelling through the years

[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)

This project contains MySQL dumps for Lahman databases (Major League Baseball) through the years.

This data has been extracted thanks to [Webucator scripts in GitHub](https://github.com/WebucatorTraining/lahman-baseball-mysql), awesome work!

[![License: CC0-1.0](https://licensebuttons.net/l/zero/1.0/80x15.png)](http://creativecommons.org/publicdomain/zero/1.0/)

Sabermetrics will set us free!

The following SQL scripts provide a database called `lahmansbaseballdb` with the following tables:

- AllStar
- Appearances
- Batting
- BattingPost
- Fielding
- FieldingOF
- FieldingOFSplit
- HomeGames
- Managers
- ManagersHalf
- Parks
- People
- Pitching
- PitchingPost
- SeriesPost
- Teams
- TeamsFranchises
- TeamsHalf

Since 2021, the following tables/files are ignored/excluded:

- Awards managers
- Awards share managers
- Awards players
- Awards share players
- College playing
- Hall of fame
- Salaries
- Schools

**Why is that?** Since Feb 25 2022, these files were moved to [another directory](https://github.com/chadwickbureau/baseballdatabank/tree/master/contrib), outside of the core in baseballdatabank of ChadwichBureau... these files are outdated (no changes since 2018), so I decided not to include them in the core database.

Also includes some tables added by Webucator:

- Leagues
- Divisions

For further information on tables and columns, read [the content guide from Sean Lahman](https://www.seanlahman.com/files/database/readme2021.txt).

## Instructions

With HeidiSQL:

- Connect to your running MySQL server
- File > Load SQL file
- Select year file

You can either:

- run the file directly on the server (without loading it in editor)
- load the file in editor (might cause large memory usage)

### Migrate to SQLite3

As Webucator indicates, you can migrate this MySQL database to SQLite with [MySQLToSQlite3 (Python package)](https://pypi.org/project/mysql-to-sqlite3/), executing the following command:

`mysql2sqlite -f lahmansbaseballdb.sqlite -d lahmansbaseballdb -u 'mysql-user' -p 'mysql-psw'`

This action can be also reversed, from [SQLite to MySQL](https://github.com/techouse/sqlite3-to-mysql).

