
```SQL
select *
from DimProduct
where EnglishProductName like '%Chainring%'
```

--Find productalternatekey where 2nd character is R
```SQL
select *
from DimProduct
where ProductAlternateKey like '_R%'
```

## Third character is '-' and fourth character is 'U'
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-U%'
```

# Any 2 characters followed by '-' followed By any 4 characters followed by '-' followed By any single character
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-____-_'
```

# Any single character within the specified range 
## Above pattern with last char L Or M 
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-____-[LM]'
```

## Above pattern with last char between L nad s
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-____-[L-S]'
```

## Above pattern with last char not between L and R
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-____-[^L-R]'
```

## Product number not starting with F
```SQL
select *
from DimProduct
where ProductAlternateKey like '[^F]%'
```

## Product number not starting with F or H
```SQL
select *
from DimProduct
where ProductAlternateKey like '[^FH]%'
```

## Product number not starting between A to H
```SQL
select *
from DimProduct
where ProductAlternateKey like '[^A-H]%'
```

## Example 1 Data(size) is the only one character  and value is from A to Z.
```SQL
select *
from DimProduct
where size like '[A-za-z][A-za-z]'
```
```SQL
select *
from DimProduct
where size like '[A-za-z]_'
```

## Text (Addressline1) rows starting with a number
```SQL
select *
from DimCustomer
where AddressLine1 like '[0-9]%'
```

# Find a number pattern
## ProductAlternateKey with a 4th and 5th characters as numbers.
```SQL
select *
from DimProduct
where ProductAlternateKey like '___[0-9][0-9]%'
```

## Number (list Dealerprice) with two decimal places ending in 2
```SQL
select *
from DimProduct
where DealerPrice like '%.[0-9]2'
```

# Using not character for regx with T-SQL
## Product number - After 1st hyphen has either number.
```SQL
select *
from DimProduct
where ProductAlternateKey like '__-[^A-Z]%'
```

## Name has only alphabetic characters
```SQL
select *
from DimProduct
where EnglishProductName like '%[^a-z]%'
```
```SQL
select *
from DimProduct
where EnglishProductName not like '%[^a-z]%'
```

## Name has no special characters
```SQL
select *
from DimProduct
where EnglishProductName like '%[^a-z0-9]%'
```
```SQL
select *
from DimProduct
where EnglishProductName not like '%[^a-z0-9]%'
```
```SQL
select *
from DimProduct
where EnglishProductName not like '%[^a-z0-9]%' and ProductAlternateKey not like '%[^a-z0-9]%'
```
