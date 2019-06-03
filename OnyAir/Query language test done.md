*Thursday, 18. May 2017 05:28PM*

# HOMEWORK DATABASE

Query language test example
All of these questions use the pgexercises database (with the bookings, facilities and members tables).

How do we access to this exercise, first open the terminal and then enter the code bellow:

```
$ pgcli pgex
```

1). How many bookings does the 'bookings' table contain? Show your SQL query.
```plsql
SELECT count(*) FROM bookings;
```

2). How many bookings with a starttime after 2012-07-01 does the 'bookings' table contain? Show your SQL query.
```plsql
SELECT count(*) from bookings WHERE starttime > '2012-07-01';
```

3). How many bookings with a starttime before 2012-08-01 does the 'bookings' table contain? Show your SQL query.
```plsql
SELECT count(*) from bookings WHERE starttime < '2012-08-01';
```

4). How many bookings in the month of July, 2012 does the 'bookings' table contain? Show your SQL query.
```plsql
SELECT count(*) from bookings WHERE starttime >= '2012-07-01' and starttime < '2012-08-01';
```

5). Give the names of the facilities which do not cost any money (are free) for members to use. Show your SQL query.
```plsql
SELECT name FROM facilities WHERE membercost = 0;
```

6). Give all facility attributes (columns), ordered by their monthlymaintenance cost. Show your SQL query.
```plsql
SELECT * FROM facilities ORDER BY monthlymaintenance;
```

7). Give all facility attributes (columns), ordered by their monthlymaintenance cost, with the most expensive ones first. Show your SQL query.
```plsql
SELECT * FROM facilities ORDER BY monthlymaintenance DESC;
```

8). Give all facility attributes (columns), ordered by their monthlymaintenance cost, with the most expensive ones first, but excluding any facility that has "Room" in the name. Show your SQL query.
```plsql
SELECT * FROM facilities WHERE name not like '%Room%' ORDER BY monthlymaintenance DESC;
```

9). Give all facility attributes (columns), ordered by their monthly maintenance cost, with the most expensive ones first, but excluding any facility that has "Room" or "room" in the name.
Your answer
```plsql
SELECT * FROM facilities WHERE (name like '%Room%') and (name like '%room%') order by monthlymaintenance DESC;
```

10). Give 'facid', 'name', 'membercost' and 'guestcost' for all facilities. Show your SQL query.
```plsql
SELECT facid, name, membercost, guestcost FROM facilities;
```

11). Give 'facid', 'name', 'membercost', 'guestcost' and "cost to members as a fraction of the cost to guests" (let's call this "memberdiscountfactor") for all facilities. Show your SQL query. For example, if the guestcost is 10, and the membercost is 5, the "memberdiscountfactor" is 5/10 = 0.5 .
```plsql
SELECT facid, name, membercost, guestcost, membercost/guestcost as memberdiscountfactor FROM facilities;
```

12). Give 'facid', 'name', 'membercost', 'guestcost' and "memberdiscountfactor" (see above question) for all facilities where this "memberdiscountfactor" is less than 0.4. Show your SQL query.
```plsql
SELECT facid, name, membercost, guestcost, membercost/guestcost as memberdiscountfactor FROM facilities WHERE membercost/guestcost < 0.4;
```

13). Give 'facid', 'name', 'membercost', 'guestcost' for all facilities, ordered by the cost to guests, cheapest first. Show your SQL query.
```plsql
SELECT facid, name, membercost, guestcost  FROM facilities order by guestcost;
```

14). Give 'facid', 'name', 'membercost', 'guestcost' for all facilities that are not free for members to use, ordered by the cost to guests, cheapest first. Show your SQL query.
```plsql
SELECT facid, name, membercost, guestcost  FROM facilities WHERE membercost ! = 0 order by guestcost;
```

15). How many facilities have a non-round number cost to members? For example, "5" and "0" are round numbers, but "3.5" and "3.4" are not. Hint: Use the modulo operator. Show your SQL query.
Your answer
```plsql
select count(*) from facilities WHERE membercost != round(membercost);
```

16). How many facilities have a non-round number cost to guests? For example, "5" and "0" are round numbers, but "3.5" and "3.4" are not. Hint: Use the modulo operator. Show your SQL query.
Your answer
```plsql
select count(*) from facilities WHERE guestcost != round(guestcost);
```


17). How many facilities have a non-round number cost to either guests or members? Show your SQL query.
Your answer
```plsql
select count(*) from facilities WHERE guestcost != round(guestcost) or membercost != round(membercost);
```


18). How many facilities have a non-round number cost to both guests and members? Show your SQL query.
Your answer
```plsql
select count(*) from facilities WHERE guestcost != round(guestcost) and membercost != round(membercost);
```

19). In the "members" table, the column 'recommendedby' expresses who recommended registering this member to the club. How many members have been recommended by another member? Show your SQL.
Your answer
```plsql
SELECT count(*) FROM members WHERE recommendedby is not null;
```

20). In the "members" table, the column 'recommendedby' expresses who recommended registering this member to the club. How many members have NOT been recommended by another member? Show your SQL.
Your answer
```plsql
SELECT "count"(*) FROM members WHERE recommendedby is null;
```

21). What is the member ID ('memid') of the user with surname "GUEST"? Show your SQL.
```plsql
SELECT memid FROM members WHERE surname = 'GUEST';
```

22). How many bookings have been made by this "GUEST" user? Show your SQL.
```plsql
SELECT count(*) FROM bookings WHERE memid=0;
```

23). How many bookings have been made by "real members" (anyone else but the "GUEST" user)? Show your SQL.
```plsql
SELECT count(*) FROM bookings WHERE memid > 0;
```


### Comprehention

```>= 2012-07-01``` sei hahu hosi dia 01
```>2012-07-01``` sei hahu hosi dia 02

### Sub query
```   plsql
SELECT * FROM ( SELECT facid, name, membercost, guestcost, membercost /  guestcost as memberdiscountfactor from cd.facilities ) as sq WHERE memberdiscountfactor < 0.4;
```

### date_part
SELECT date_part('month', starttime) FROM bookings LIMIT 5;
SELECT date_part('hour', starttime) FROM bookings LIMIT 5;



# Wednesday; September 05 of 2018

### Django  

```````
$ ./manage.py inspectdb members
$ ./manage.py 
$
$
$
$
```````

