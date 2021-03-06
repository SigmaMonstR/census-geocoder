# R wrapper to geocode addresses using the US Census Bureau's geocoder

Wrapper accepts serial calls using either

1. Address, Zipcode, State; or
2. Address, City, State

Each call kicks back a data frame with the matched address, lat + lon in WGS84, the FIPS for the Census tract and the FIPS for the Census block.  

## Syntax

### census_geocoder(address, type,secondary,state)

- address = a string with the bldg number + address (e.g. 1600 Pennsylvania Ave)
- type = a code representing the type of secondary information. "z" = zipcode, "c" = city
- secondary = the sub-state identifier corresponding the the type specified above (zipcode 20815 would correspond with z, Bethesda would correspond with c)
- state = 2-letter state abbreviation

### examples
```
census_geocoder("1600 Pennsylvania Ave","c","Washington","DC") 

census_geocoder("253 Broadway","z","10007","NY") 


address <- c("1800 F Street NW", "1600 Pennsylvania Av")

type <- c("z","c")

secondary <- c("20006","Washington DC")

state <- c("DC","DC")

for(i in 1:length(address)){
  census_geocoder(address[i], type[i], secondary[i], state[i])      
      }
```


