# Worldometers.info API
## 0. Progress
- [Get global COVID-19 totals for today, yesterday and two days ago](#get-global) 
- [Get COVID-19 totals for all continents](#get-all-continents)
- [Get COVID-19 totals for a specific continent](#get-a-continent)
- [Get COVID-19 totals for all countries](#get-all-countries)
- [Get COVID-19 totals for a specific country](#get-a-country)
- [Get COVID-19 totals for a specific set of countries](#get-a-set-of-countries)
## 1. Foreword
This document is for learning purpose only. 
- Original source: [disease.sh Docs](https://disease.sh/docs/)
## 2. API
### Get global

Parameters
```
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1 
	- allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
	

Syntax:
```
GET 'https://disease.sh/v3/covid-19/all?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&allowNull={BOOLEAN}'
```
Example return: (from 21-Nov-21)
```JSON
{
	"updated": 1637569668690,
	"cases":257825665,
	"todayCases":396038,
	"deaths":5167917,
	"todayDeaths":4432,
	"recovered":232715756,
	"todayRecovered":329524,
	"active":19941992,
	"critical":79729,
	"casesPerOneMillion":33077,
	"deathsPerOneMillion":663,
	"tests":4203696655,
	"testsPerOneMillion":534542.93,
	"population":7864095554,
	"oneCasePerPeople":0,
	"oneDeathPerPeople":0,
	"oneTestPerPeople":0,
	"activePerOneMillion":2535.83,
	"recoveredPerOneMillion":29592.18,
	"criticalPerOneMillion":10.14,
	"affectedCountries":224
}
```
### Get all continents

Parameters
```
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
sort = {KEY} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1
	- KEY = [cases, todayCases, deaths, recovered, active]
	- allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
	

Syntax:
```
GET 'https://disease.sh/v3/covid-19/continents?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&sort={KEY}&allowNull={BOOLEAN}'
```
Example return:
```JSON
{
    "updated": 1637572062757,
    "cases": 81315549,
    "todayCases": 79357,
    "deaths": 1201225,
    "todayDeaths": 1191,
    "recovered": 78564249,
    "todayRecovered": 103256,
    "active": 1550075,
    "critical": 29089,
    "casesPerOneMillion": 17462.91,
    "deathsPerOneMillion": 257.97,
    "tests": 1566510562,
    "testsPerOneMillion": 336415.85,
    "population": 4656470769,
    "continent": "Asia",
    "activePerOneMillion": 332.89,
    "recoveredPerOneMillion": 16872.06,
    "criticalPerOneMillion": 6.25,
    "continentInfo": {
      "lat": 23.7027273,
      "long": 62.3750637
    },
    "countries": [
      "Afghanistan",
      "Armenia",
      "Azerbaijan",
      "Bahrain",
      "Bangladesh",
      "Bhutan",
      "Brunei",
      "Cambodia",
	  ....
    ]
  },
  {
    "updated": 1637572062760,
    "cases": 70463275,
    "todayCases": 262774,
    "deaths": 1379957,
    "todayDeaths": 2528,
    "recovered": 62039265,
    "todayRecovered": 183742,
    "active": 7044053,
    "critical": 17992,
    "casesPerOneMillion": 94169.88,
    "deathsPerOneMillion": 1844.23,
    "tests": 1498332845,
    "testsPerOneMillion": 2002430.63,
    "population": 748257056,
    "continent": "Europe",
    "activePerOneMillion": 9413.95,
    "recoveredPerOneMillion": 82911.7,
    "criticalPerOneMillion": 24.05,
    "continentInfo": {
      "lat": 25.771324,
      "long": -35.6012256
    },
    "countries": [
      "Albania",
      "Andorra",
      "Austria",
      "Belarus",
      "Belgium",
      "Bosnia",
      "Bulgaria",
      "Channel Islands",
      "Croatia",
      "Czechia",
      "Denmark",
      "Estonia",
      "Faroe Islands",
      "Finland",
	  ....
    ]
  },
  {
    "updated": 1637572062758,
    "cases": 58211708,
    "todayCases": 34599,
    "deaths": 1182120,
    "todayDeaths": 364,
    "recovered": 46859232,
    "todayRecovered": 26469,
    "active": 10170356,
    "critical": 18055,
    "casesPerOneMillion": 97750.35,
    "deathsPerOneMillion": 1985.04,
    "tests": 830491289,
    "testsPerOneMillion": 1394578.77,
    "population": 595514078,
    "continent": "North America",
    "activePerOneMillion": 17078.28,
    "recoveredPerOneMillion": 78687.03,
    "criticalPerOneMillion": 30.32,
    "continentInfo": {
      "lat": 31.6768272,
      "long": -146.4707474
    },
    "countries": [
      "Anguilla",
      "Antigua and Barbuda",
      "Aruba",
      "Bahamas",
      "Barbados",
      "Belize",
      "Bermuda",
      "British Virgin Islands",
      "Canada",
	  .....
    ]
  },
  {
    "updated": 1637572062759,
    "cases": 38819876,
    "todayCases": 14217,
    "deaths": 1178359,
    "todayDeaths": 227,
    "recovered": 36904879,
    "todayRecovered": 11098,
    "active": 736638,
    "critical": 12507,
    "casesPerOneMillion": 89099.54,
    "deathsPerOneMillion": 2704.57,
    "tests": 177116013,
    "testsPerOneMillion": 406517.39,
    "population": 435691107,
    "continent": "South America",
    "activePerOneMillion": 1690.73,
    "recoveredPerOneMillion": 84704.23,
    "criticalPerOneMillion": 28.71,
    "continentInfo": {
      "lat": -15.6551563,
      "long": -100.7484231
    },
    "countries": [
      "Argentina",
      "Bolivia",
      "Brazil",
      "Chile",
      "Colombia",
      "Ecuador",
      "Falkland Islands (Malvinas)",
      "French Guiana",
      "Guyana",
      "Paraguay",
      "Peru",
      "Suriname",
      "Uruguay",
      "Venezuela"
    ]
  },
  {
    "updated": 1637572062761,
    "cases": 8661257,
    "todayCases": 3048,
    "deaths": 222157,
    "todayDeaths": 113,
    "recovered": 8041830,
    "todayRecovered": 4430,
    "active": 397270,
    "critical": 1904,
    "casesPerOneMillion": 6253.39,
    "deathsPerOneMillion": 160.4,
    "tests": 79173602,
    "testsPerOneMillion": 57163,
    "population": 1385049800,
    "continent": "Africa",
    "activePerOneMillion": 286.83,
    "recoveredPerOneMillion": 5806.17,
    "criticalPerOneMillion": 1.37,
    "continentInfo": {
      "lat": 1.7383867,
      "long": -16.3094636
    },
    "countries": [
      "Algeria",
      "Angola",
      "Benin",
      "Botswana",
      "Burkina Faso",
      "Burundi",
      "Cabo Verde",
      "Cameroon",
      "Central African Republic",
      "Chad",
      "Comoros",
      "Congo",
	  .....
    ]
  },
  {
    "updated": 1637572062762,
    "cases": 353279,
    "todayCases": 2043,
    "deaths": 4084,
    "todayDeaths": 9,
    "recovered": 305595,
    "todayRecovered": 529,
    "active": 43600,
    "critical": 182,
    "casesPerOneMillion": 8194.31,
    "deathsPerOneMillion": 94.73,
    "tests": 52072343,
    "testsPerOneMillion": 1207817.88,
    "population": 43112744,
    "continent": "Australia-Oceania",
    "activePerOneMillion": 1011.3,
    "recoveredPerOneMillion": 7088.28,
    "criticalPerOneMillion": 4.22,
    "continentInfo": {
      "lat": -8.6599161,
      "long": 91.1469847
    },
    "countries": [
      "Australia",
      "Fiji",
      "French Polynesia",
      "Marshall Islands",
      "Micronesia",
      "New Caledonia",
      "New Zealand",
      "Palau",
      "Papua New Guinea",
      "Samoa",
      "Solomon Islands",
      "Tonga",
      "Vanuatu",
      "Wallis and Futuna"
    ]
  }
```
### Get a continent

Parameters
```
continent = {KEY} (required)
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
strict = {BOOLEAN} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1 
	- KEY = [Asia, Africa, North America, South America, Antarctica, Europe, Australia]
	- strict: Setting to false gives you the ability to fuzzy search continents (i.e. Oman vs. rOMANia), default value: True
    - allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
    

Syntax:
```
GET 'https://disease.sh/v3/covid-19/continents/continent={KEY}?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&strict={BOOLEAN}&allowNull={BOOLEAN}'
```
Example return:
```JSON
{
  "updated":  1637573257263,
  "cases":  81329966,  
  "todayCases":  14417, 
  "deaths":  1201635, 
  "todayDeaths":  410, 
  "recovered":  78597184,  
  "todayRecovered":  32935,  
  "active":  1531147,  
  "critical":  28813,  
  "casesPerOneMillion":  17466.01,  
  "deathsPerOneMillion":  258.06,  
  "tests":  1567539231,  
  "testsPerOneMillion":  336636.76,  
  "population":  4656470769,  
  "continent":  "Asia",  
  "activePerOneMillion":  328.82,  
  "recoveredPerOneMillion":  16879.13,  
  "criticalPerOneMillion":  6.19,  
  "continentInfo":  
  {  
	  "lat":  23.7027273,  
	  "long":  62.3750637  
  },  
  "countries":  
  [  
	  "Afghanistan",  
	  "Armenia",  
	  "Azerbaijan",  
	  "Bahrain",  
	  "Bangladesh",  
	  "Bhutan",  
	  "Brunei",  
	  "Cambodia",  
	  "China",  
	  "Cyprus",  
	  "Georgia",  
	  "Hong Kong",  
	  "India",  
	  "Indonesia",  
	  "Iran",  
	  "Iraq",  
	  "Israel",  
	  "Japan",  
	  "Jordan",  
	  "Kazakhstan",  
	  "Kuwait",  
	  "Kyrgyzstan",  
	  "Lao People's Democratic Republic",  
	  "Lebanon",  
	  "Macao",  
	  "Malaysia",  
	  "Maldives",  
	  "Mongolia",  
	  "Myanmar",  
	  "Nepal",  
	  "Oman",  
	  "Pakistan",  
	  "Palestine",  
	  "Philippines",  
	  "Qatar",  
	  "S. Korea",  
	  "Saudi Arabia",  
	  "Singapore",  
	  "Sri Lanka",  
	  "Syrian Arab Republic",  
	  "Taiwan",  
	  "Tajikistan", 
	  "Thailand",  
	  "Timor-Leste",  
	  "Turkey",  
	  "UAE",  
	  "Uzbekistan",  
	  "Vietnam",  
	  "Yemen"  
	  ]  
}
```
### Get all countries

Parameters
```
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
sort = {KEY} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1
	- KEY = [cases, todayCases, deaths, recovered, active]
	- allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
	

Syntax:
```
GET 'https://disease.sh/v3/covid-19/countries?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&sorts={KEY}&allowNull={BOOLEAN}'
```
Example return: (from 21-Nov-21)
```JSON
{
    "updated": 1637573857468,
    "country": "USA",
    "countryInfo": 
    {
      "_id": 840,
      "iso2": "US",
      "iso3": "USA",
      "lat": 38,
      "long": -97,
      "flag": "https://disease.sh/assets/img/flags/us.png"
    },
    "cases": 48592810,
    "todayCases": 27484,
    "deaths": 793651,
    "todayDeaths": 96,
    "recovered": 38463041,
    "todayRecovered": 20189,
    "active": 9336118,
    "critical": 11775,
    "casesPerOneMillion": 145620,
    "deathsPerOneMillion": 2378,
    "tests": 739889385,
    "testsPerOneMillion": 2217252,
    "population": 333696583,
    "continent": "North America",
    ...
}
```
### Get a country

Parameters
```
country = {KEY} (required)
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
strict = {BOOLEAN} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1 
	- KEY = [country name, iso2, iso3, country ID code]
	strict: Setting to false gives you the ability to fuzzy search continents (i.e. Oman vs. rOMANia), default value: True
	- allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
	

Syntax:
```
GET 'https://disease.sh/v3/covid-19/countries/country={KEY}?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&strict={BOOLEAN}&allowNull={BOOLEAN}'
```
Example return: (from 21-Nov-21)
```JSON
{
    "updated":  1637574456261,  
    "country":  "Vietnam",  
    "countryInfo":  
    {  
	    "_id":  704,  
	    "iso2":  "VN",  
	    "iso3":  "VNM",  
	    "lat":  21,  
	    "long":  105.8,  
	    "flag":  "https://disease.sh/assets/img/flags/vn.png"  
	},  
	"cases":  1094514,  
	"todayCases":  0,  
	"deaths":  23761,  
	"todayDeaths":  0,  
	"recovered":  905500,  
	"todayRecovered":  0,  
	"active":  165253,  
	"critical":  5163,  
	"casesPerOneMillion":  11106,  
	"deathsPerOneMillion":  241,  
	"tests":  65891104,  
	"testsPerOneMillion":  668580,  
	"population":  98553778,  
	"continent":  "Asia",  
	"oneCasePerPeople":  90,  
	"oneDeathPerPeople":  4148,  
	"oneTestPerPeople":  1,  
	"activePerOneMillion":  1676.78,  
	"recoveredPerOneMillion":  9187.88,  
	"criticalPerOneMillion":  52.39
}
```
### Get a set of countries

Parameters
```
countries = {KEY} (required)
yesterday = {BOOLEAN} (optional)
twoDaysAgo = {BOOLEAN} (optional)
allowNull = {BOOLEAN} (optional)
```
- **Remember**:
	- BOOLEAN: can be True/False, 0/1 
	- KEY = [multiple country names, iso2, iso3, country IDs code], seperated by commas
	- allowNull: By default, if a value is missing, it is returned as 0. This allows nulls to be returned
	

Syntax:
```
GET 'https://disease.sh/v3/covid-19/countries/countries={KEY}?yesterday={BOOLEAN}||twoDaysAgo={BOOLEAN}&allowNull={BOOLEAN}'
```
### 
 - [Home](#get-global)

