# SQL-EX.RU exercises
## Databases description 
[Link](https://www.sql-ex.ru/help/select13.php#db_3)

### 1. Computer firm
The database scheme consists of four tables:
- **Product** (maker, model, type)
- **PC** (code, model, speed, ram, hd, cd, price)
- **Laptop** (code, model, speed, ram, hd, screen, price)
- **Printer** (code, model, color, type, price)

The **Product** table contains data on the maker, model number, and type of product ('PC', 'Laptop', or 'Printer'). It is assumed that model numbers in the Product table are unique for all makers and product types. 

Each personal computer in the **PC** table is unambiguously identified by a unique code, and is additionally characterized by its model (foreign key referring to the Product table), processor speed (in MHz) – speed field, RAM capacity (in Mb) - ram, hard disk drive capacity (in Gb) – hd, CD-ROM speed (e.g, '4x') - cd, and its price. 

The **Laptop** table is similar to the PC table, except that instead of the CD-ROM speed, it contains the screen size (in inches) – screen. 

For each printer model in the **Printer** table, its output type (‘y’ for color and ‘n’ for monochrome) – color field, printing technology ('Laser', 'Jet', or 'Matrix') – type, and price are specified.

![image](https://user-images.githubusercontent.com/85280942/130974674-cea0b26c-1709-4820-b476-eee77ea0a78d.png)


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

``` sql

```

### Task 3

``` sql

```

### Task 4

``` sql

```

### Task 5

``` sql

```

### Task 6

``` sql

```

### Task 7

``` sql

```

### Task 8

``` sql

```

### Task 9

``` sql

```

### Task 10

``` sql

```

### Task 11

``` sql

```

### Task 12

``` sql

```

### Task 13

``` sql

```

### Task 14

``` sql

```

### Task 15

``` sql

```

### Task 16

``` sql

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

```

### Task 52

``` sql

```

### Task 53

``` sql

```

### Task 54

``` sql

```

### Task 55

For each class, determine the year the first ship of this class was launched.
If the lead ship’s year of launch is not known, get the minimum year of launch for the ships of this class.
Result set: class, year.

``` sql

```

### Task 56

``` sql

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
