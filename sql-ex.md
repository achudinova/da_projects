# SQL-EX.RU exercises
## Databases description 
[Link to Appendix 1. About educational databases](https://www.sql-ex.ru/help/select13.php#db_3)

### 1. Computer firm
![image](https://user-images.githubusercontent.com/85280942/130974674-cea0b26c-1709-4820-b476-eee77ea0a78d.png)

The database scheme consists of four tables:
- **Product** (maker, model, type)
- **PC** (code, model, speed, ram, hd, cd, price)
- **Laptop** (code, model, speed, ram, hd, screen, price)
- **Printer** (code, model, color, type, price)

The **Product** table contains data on the maker, model number, and type of product ('PC', 'Laptop', or 'Printer'). It is assumed that model numbers in the Product table are unique for all makers and product types. 

Each personal computer in the **PC** table is unambiguously identified by a unique code, and is additionally characterized by its model (foreign key referring to the Product table), processor speed (in MHz) – speed field, RAM capacity (in Mb) - ram, hard disk drive capacity (in Gb) – hd, CD-ROM speed (e.g, '4x') - cd, and its price. 

The **Laptop** table is similar to the PC table, except that instead of the CD-ROM speed, it contains the screen size (in inches) – screen. 

For each printer model in the **Printer** table, its output type (‘y’ for color and ‘n’ for monochrome) – color field, printing technology ('Laser', 'Jet', or 'Matrix') – type, and price are specified.

### 2. Recycling firm
![image](https://www.sql-ex.ru/images/income.gif)

The firm owns several buy-back centers for collection of recyclable materials. Each of them receives funds to be paid to the recyclables suppliers. 

Data on funds received is recorded in the table
- **Income_o** (point, date, inc)

The primary key is (point, date), where point holds the identifier of the buy-back center, and date corresponds to the calendar date the funds were received. 
The date column doesn’t include the time part, thus, money (inc) arrives no more than once a day for each center. 

Information on payments to the recyclables suppliers is held in the table 
- **Outcome_o** (point, date, out)

In this table, the primary key (point, date) ensures each buy-back center reports about payments (out) no more than once a day, too.

For the case income and expenditure may occur more than once a day, another database schema with tables having a primary key consisting of the single column code is used:

- **Income** (code, point, date, inc)
- **Outcome** (code, point, date, out)

Here, the date column doesn’t include the time part, either.

### 3. Ships
![image](https://www.sql-ex.ru/images/ships.gif)

The database of naval ships that took part in World War II is under consideration. 

The database consists of the following relations:
 - **Classes** (class, type, country, numGuns, bore, displacement)
 - **Ships** (name, class, launched)
 - **Battles** (name, date)
 - **Outcomes** (ship, battle, result)

Ships in classes all have the same general design.<br>
A class is normally assigned either the name of the first ship built according to the corresponding design, or a name that is different from any ship name in the database. The ship whose name is assigned to a class is called a lead ship.

The **Classes** relation includes the name of the class, type (can be either bb for a battle ship, or bc for a battle cruiser), country the ship was built in, the number of main guns, gun caliber (bore diameter in inches), and displacement (weight in tons). 

The **Ships** relation holds information about the ship name, the name of its corresponding class, and the year the ship was launched. 

The **Battles** relation contains names and dates of battles the ships participated in. 

The **Outcomes** relation - the battle result for a given ship (may be sunk, damaged, or OK, the last value meaning the ship survived the battle unharmed).

Notes: 
 1. The Outcomes relation may contain ships not present in the Ships relation.
 2. A ship sunk can’t participate in later battles. 
 3. For historical reasons, lead ships are referred to as head ships in many exercises.
 4. A ship found in the Outcomes table but not in the Ships table is still considered in the database. This is true even if it is sunk.

CLASS	        |TYPE	|COUNTRY    |NUMGUNS    |BORE   |DISPLACEMENT
----------------|-------|-----------|-----------|-------|--------
Bismarck        |bb     |Germany    |8	        |15	    |42000
Iowa            |bb     |USA	    |9	        |16	    |46000
Kongo	        |bc     |Japan      |8	        |14	    |32000
North Carolina	|bb     |USA	    |12	        |16	    |37000
Renown	        |bc	    |Gt.Britain	|6	        |15	    |32000
Revenge	        |bb	    |Gt.Britain	|8	        |15	    |29000
Tennessee	    |bb	    |USA	    |12	        |14	    |32000
Yamato	        |bb     |Japan	    |9          |18	    |65000

NAME			|CLASS			|LAUNCHED
----------------|---------------|--------
California		|Tennessee		|1921
Haruna			|Kongo			|1916
Hiei			|Kongo			|1914
Iowa			|Iowa			|1943
Kirishima		|Kongo			|1915
Kongo			|Kongo			|1913
Missouri		|Iowa			|1944
Musashi			|Yamato			|1942
New Jersey		|Iowa			|1943
North Carolina	|North Carolina	|1941
Ramillies		|Revenge		|1917
Renown			|Renown			|1916
Repulse			|Renown			|1916
Resolution		|Renown			|1916
Revenge			|Revenge		|1916
Royal Oak		|Revenge		|1916
Royal Sovereign	|Revenge		|1916
Tennessee		|Tennessee		|1920
Washington		|North Carolina	|1941
Wisconsin		|Iowa			|1944
Yamato			|Yamato			|1941
South Dakota	|North Carolina	|1941


SHIP			|BATTLE			|RESULT
----------------|---------------|--------
Bismarck		|North Atlantic	|sunk
California		|Surigao Strait	|OK
Duke of York	|North Cape		|OK
Fuso			|Surigao Strait	|sunk
Hood			|North Atlantic	|sunk
King George V	|North Atlantic	|OK
Kirishima		|Guadalcanal	|sunk
Prince of Wales	|North Atlantic	|damaged
Rodney			|North Atlantic	|OK
Schamhorst		|North Cape		|sunk
South Dakota	|Guadalcanal	|damaged
Tennessee		|Surigao Strait	|OK
Washington		|Guadalcanal	|OK
West Virginia	|Surigao Strait	|OK
Yamashiro		|Surigao Strait	|sunk
California		|Guadalcanal	|damaged

### 4. Airport
![image](https://www.sql-ex.ru/images/aero.gif)

The database schema consists of 4 tables:
 - **Company** (ID_comp, name)
 - **Trip** (trip_no, id_comp, plane, town_from, town_to, time_out, time_in)
 - **Passenger** (ID_psg, name)
 - **Pass_in_trip** (trip_no, date, ID_psg, place)

The **Company** table contains IDs and names of the airlines transporting passengers. 

The **Trip** table contains information on the schedule of flights: trip (flight) number, company (airline) ID, plane type, departure city, destination city, departure time, and arrival time. 

The **Passenger** table holds IDs and names of the passengers. The Pass_in_trip table contains data on flight bookings: trip number, departure date (day), passenger ID and her seat (place) designation during the flight. 

It should be noted that
- scheduled flights are operated daily; the duration of any flight is less than 24 hours; town_from <> town_to;
- all time and date values are assumed to belong to the same time zone;
- departure and arrival times are specified with one minute precision;
- there can be several passengers bearing the same first name and surname (for example, Bruce Willis);
- the seat (place) designation consists of a number followed by a letter; the number stands for the row, while the letter (a – d) defines the seat position in the grid (from left to right, in alphabetical order;
- connections and constraints are shown in the database schema below.

### 5. Painting
![image](https://www.sql-ex.ru/images/painting.gif)

The database schema consists of 3 tables:

 - **utQ** (Q_ID int, Q_NAME varchar(35)) 
 - **utV** (V_ID int, V_NAME varchar(35), V_COLOR char(1))
 - **utB** (B_DATETIME datetime, B_Q_ID int, B_V_ID int, B_VOL tinyint)

The **utQ** table contains the identifiers and names of squares, the initial color of which is black. (Note: black is not a color and is considered unpainted. Only Red, Green and Blue are colors.)

The **utV** table contains the identifiers and names of spray cans and the color of paint they are filled with.

The **utB** table holds information on squares being spray-painted, and contains the time of the painting event, the square and spray can identifiers, the quantity of paint being applied.

It should be noted that
- a spray can may contain paint of one of three colors: red (V_COLOR='R'), green (V_COLOR='G'), or blue (V_COLOR='B');
- any spray can initially contains 255 units of paint;
- the square color is defined in accordance with the RGB model, i.e. R=0, G=0, B=0 is black, whereas R=255, G=255, B=255 is white;
- any record in the utB table decreases the paint quantity in the corresponding spray can by B_VOL and accordingly increases the amount of paint applied to the square by the same value;
- B_VOL must be greater than 0 and less or equal to 255;
- the paint quantity of a single color applied to one square can’t exceed 255, and there can’t be a less than zero amount of paint in a spray can;
- the time of the painting event (B_DATETIME) is specified with one second precision, i.e. it does not contain milliseconds;
- for historical reasons, the spray cans are referred to as “balloons” by many of the exercises, and the utV table contains spray can names (V_NAME column) such as “Balloon # 01”, etc.



## Solutions

### Task 1 

Find the model number, speed and hard drive capacity for all the PCs with prices below $500. Result set: model, speed, hd.

``` sql
SELECT 
  model,
  speed,
  hd 
FROM PC
WHERE price < 500
```

### Task 2

List all printer makers. Result set: maker.

``` sql
SELECT DISTINCT MAKER FROM Product
WHERE type='Printer'
```

### Task 3

Find the model number, RAM and screen size of the laptops with prices over $1000.

``` sql
SELECT model,ram,screen FROM Laptop
WHERE price >1000
```

### Task 4

Find all records from the Printer table containing data about color printers.

``` sql
SELECT * FROM PRINTER
WHERE color ='Y'
```

### Task 5

Find the model number, speed and hard drive capacity of PCs cheaper than $600 having a 12x or a 24x CD drive.

``` sql
SELECT MODEL,SPEED,HD 
FROM PC
WHERE (CD='12x' OR CD='24x')
AND PRICE<600
```

### Task 6

For each maker producing laptops with a hard drive capacity of 10 Gb or higher, find the speed of such laptops. Result set: maker, speed.

``` sql
SELECT DISTINCT Product.maker, Laptop.speed
FROM 
Product INNER JOIN laptop ON Laptop.model = Product.model 
WHERE (Laptop.hd >= 10) AND PRODUCT.TYPE='laptop'

```

### Task 7

Get the models and prices for all commercially available products (of any type) produced by maker B.

``` sql
SELECT  PC.model, price
FROM PC INNER JOIN   
     Product ON PC.model = Product.model
     where Product.maker='b'
   
UNION
SELECT Laptop.model, price 
FROM Laptop INNER JOIN   
     Product ON Laptop.model = Product.model
     where Product.maker='b'
UNION

SELECT printer.model, price 
FROM printer INNER JOIN   
     Product ON printer.model = Product.model
     where Product.maker='b'

```

### Task 8

Find the makers producing PCs but not laptops.

``` sql
select maker 
from Product
where product.type in ('PC','Laptop')

except

select maker 
from Product
where product.type='laptop'
```

### Task 9

Find the makers of PCs with a processor speed of 450 MHz or more. Result set: maker.

``` sql
select distinct product.maker 
from Product 
join PC ON PC.model = Product.model 
where (PC.speed >= 450)
```

### Task 10

Find the printer models having the highest price. Result set: model, price.

``` sql
select distinct model, price 
from printer 
where price = (Select max(price) from printer)
```

### Task 11

Find out the average speed of PCs.

``` sql
select avg (speed) as AVG_Speed 
from pc
```

### Task 12

Find out the average speed of the laptops priced over $1000.

``` sql
select avg(speed) as avg_speed 
from laptop
where price > 1000
```

### Task 13

Find out the average speed of the PCs produced by maker A.

``` sql
select avg(pc.speed) as avg_speed 
from pc
join product 
on product.model = pc.model
where product.maker='A'
```

### Task 14

For the ships in the Ships table that have at least 10 guns, get the class, name, and country.

``` sql
select 
    s.class, 
    s.name, 
    c.country 
from ships s
join classes c on s.class = c.class
where numguns > 9
```

### Task 15

Get hard drive capacities that are identical for two or more PCs.
Result set: hd.

``` sql
select distinct hd 
from pc
where exists (  select 'x' 
                from pc p
                where p.code <> pc.code
                and p.hd = pc.hd)
```

### Task 16

Get pairs of PC models with identical speeds and the same RAM capacity. Each resulting pair should be displayed only once, i.e. (i, j) but not (j, i).
Result set: model with the bigger number, model with the smaller number, speed, and RAM.

! doesn't work with ORACLE

``` sql
SELECT distinct 
    pc1.model as model1, 
    pc2.model as model2, 
    pc1.speed, 
    pc1.ram
FROM pc AS pc1, pc AS pc2
WHERE pc1.model > pc2.model 
    AND pc1.speed = pc2.speed 
    AND pc1.ram = pc2.ram
```

### Task 17

``` sql

```

### Task 18

``` sql

```

### Task 19

``` sql

```

### Task 20

``` sql

```

### Task 21

``` sql

```

### Task 22

``` sql

```

### Task 23

``` sql

```

### Task 24

``` sql

```

### Task 25

``` sql

```

### Task 26

``` sql

```

### Task 27

``` sql

```

### Task 28

``` sql

```

### Task 29

``` sql

```

### Task 30

``` sql

```

### Task 31

``` sql

```

### Task 32

``` sql

```

### Task 33

``` sql

```

### Task 34

``` sql

```

### Task 35

``` sql

```

### Task 36

``` sql

```

### Task 37

``` sql

```

### Task 38

``` sql

```

### Task 39

``` sql

```

### Task 40

``` sql

```

### Task 41

``` sql

```

### Task 42

``` sql

```

### Task 43

``` sql

```

### Task 44

``` sql

```

### Task 45

``` sql

```

### Task 46

``` sql

```

### Task 47

``` sql

```

### Task 48

``` sql

```

### Task 49

``` sql

```

### Task 50

``` sql

```

### Task 51

``` sql
WITH a AS 
(SELECT 
    name AS ship, 
    numGuns, 
    displacement
FROM classes c
JOIN ships s
    ON s.class = c.class

UNION
SELECT 
    ship AS ship, 
    numGuns, 
    displacement
FROM outcomes o
JOIN classes c
    ON o.ship = c.class)

select 
    a.ship
from a
join 
    (select 
        DISPLACEMENT, 
        max(NUMGUNS) maxng
    from a
    group by DISPLACEMENT) b
on a.DISPLACEMENT = b.DISPLACEMENT 
    and a.numGuns = b.maxng
```

### Task 52

``` sql
select
    s.name
from ships s
join classes c 
    on c.class = s.class
where (c.country = 'Japan' or c.country is null)
    and (c.type = 'bb' or c.type is null)
    and (c.numguns >= 9 or c.numguns is null)
    and (c.bore < 19 or c.bore is null)
    and (c.displacement <= 65000 or c.displacement  is null)
```

### Task 53

``` sql
select 
    round(avg(numGuns),2) avg_numguns
from classes c
where c.type = 'bb'
```

### Task 54

With a precision of two decimal places, determine the average number of guns for all battleships (including the ones in the Outcomes table).

``` sql
select round(avg(numguns),2) 
from
    (select
        s.name, 
        c.numguns, 
        c.type
    from ships s 
    join classes c on s.class = c.class
    
    union
    
    select 
        o.ship, 
        c.numguns, 
        c.type
    from outcomes o
    join classes c on c.class = o.ship
    where o.ship not in (select name from ships) ) t
where type = 'bb'
```

### Task 55

For each class, determine the year the first ship of this class was launched.
If the lead ship’s year of launch is not known, get the minimum year of launch for the ships of this class.
Result set: class, year.

``` sql
select 
    c.class,
    min(s.launched)
from classes c 
left join ships s
    on c.class = s.class
group by c.class
```

### Task 56

For each class, find out the number of ships of this class that were sunk in battles.
Result set: class, number of ships sunk.

``` sql
with sun as (
select
nvl(s.class, o.ship) as class,
count(*) sunks
from outcomes o
left join ships s on o.ship = s.name
where result = 'sunk'
group by nvl(s.class, o.ship))

select 
c.class,
nvl(s.sunks,0) sunks
from classes c 
left join sun s
on c.class = s.class
```

### Task 57

``` sql

```

### Task 58

``` sql

```

### Task 59

``` sql

```

### Task 60

``` sql

```

### Task 61

``` sql

```

### Task 62

``` sql

```

### Task 63

``` sql

```

### Task 64

``` sql

```

### Task 65

``` sql

```

### Task 66

``` sql

```

### Task 67

``` sql

```

### Task 68

``` sql

```

### Task 69

``` sql

```

### Task 70

``` sql

```

### Task 71

``` sql

```

### Task 72

``` sql

```

### Task 73

``` sql

```

### Task 74

``` sql

```

### Task 75

``` sql

```

### Task 76

``` sql

```

### Task 77

``` sql

```

### Task 78

``` sql

```

### Task 79

``` sql

```

### Task 80

``` sql

```

### Task 81

``` sql

```

### Task 82

``` sql

```

### Task 83

``` sql

```

### Task 84

``` sql

```

### Task 85

``` sql

```

### Task 86

``` sql

```

### Task 87

``` sql

```

### Task 88

``` sql

```

### Task 89

``` sql

```

### Task 90

``` sql

```

### Task 91

``` sql

```

### Task 92

``` sql

```

### Task 93

``` sql

```

### Task 94

``` sql

```

### Task 95

``` sql

```

### Task 96

``` sql

```

### Task 97

``` sql

```

### Task 98

``` sql

```

### Task 99

``` sql

```

### Task 100

``` sql

```

### Task 101

``` sql

```

### Task 102

``` sql

```

### Task 103

``` sql

```

### Task 104

``` sql

```

### Task 105

``` sql

```

### Task 106

``` sql

```

### Task 107

``` sql

```

### Task 108

``` sql

```

### Task 109

``` sql

```

### Task 110

``` sql

```

### Task 111

``` sql

```

### Task 112

``` sql

```

### Task 113

``` sql

```

### Task 114

``` sql

```

### Task 115

``` sql

```

### Task 116

``` sql

```

### Task 117

``` sql

```

### Task 118

``` sql

```

### Task 119

``` sql

```

### Task 120

``` sql

```

### Task 121

``` sql

```

### Task 122

``` sql

```

### Task 123

``` sql

```

### Task 124

``` sql

```

### Task 125

``` sql

```

### Task 126

``` sql

```

### Task 127

``` sql

```

### Task 128

``` sql

```

### Task 129

``` sql

```

### Task 130

``` sql

```

### Task 131

``` sql

```

### Task 132

``` sql

```

### Task 133

``` sql

```

### Task 134

``` sql

```

### Task 135

``` sql

```

### Task 136

``` sql

```

### Task 137

``` sql

```

### Task 138

``` sql

```

### Task 139

``` sql

```

### Task 140

``` sql

```

### Task 141

``` sql

```

### Task 142

``` sql

```

### Task 143

``` sql

```

### Task 144

``` sql

```

### Task 145

``` sql

```

### Task 146

``` sql

```

### Task 147

``` sql

```

### Task 148

``` sql

```

### Task 149

``` sql

```

### Task 150

``` sql

```

### Task 151

``` sql

```

### Task 152

``` sql

```

### Task 153

``` sql

```

### Task 154

``` sql

```

### Task 155

``` sql

```

### Task 156

``` sql

```
