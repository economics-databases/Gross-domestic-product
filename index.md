### 1. GDP growth (annual %)

* Annual percentage growth rate of GDP at market prices based on constant local currency. Aggregates are based on constant 2010 U.S. dollars. GDP is the sum of gross value added by all resident producers in the economy plus any product taxes and minus any subsidies not included in the value of the products. It is calculated without making deductions for depreciation of fabricated assets or for depletion and degradation of natural resources.

* Periodicity: Annual

* Source: [World Bank](https://data.worldbank.org) national accounts data

[CSV](https://raw.githubusercontent.com/economics-databases/Gross-domestic-product/GDP_PCT_A.csv)

### 2. GDP (current US$) 

* GDP at purchaser's prices is the sum of gross value added by all resident producers in the economy plus any product taxes and minus any subsidies not included in the value of the products. It is calculated without making deductions for depreciation of fabricated assets or for depletion and degradation of natural resources. Data are in current U.S. dollars. Dollar figures for GDP are converted from domestic currencies using single year official exchange rates. For a few countries where the official exchange rate does not reflect the rate effectively applied to actual foreign exchange transactions, an alternative conversion factor is used.

* Periodicity: Annual

* Source: [World Bank](https://data.worldbank.org) national accounts data

### 3. GDP per capita growth (annual %)

* Annual percentage growth rate of GDP per capita based on constant local currency. Aggregates are based on constant 2010 U.S. dollars. GDP per capita is gross domestic product divided by midyear population. GDP at purchaser's prices is the sum of gross value added by all resident producers in the economy plus any product taxes and minus any subsidies not included in the value of the products. It is calculated without making deductions for depreciation of fabricated assets or for depletion and degradation of natural resources.

* Periodicity: Annual

* Source: [World Bank](https://data.worldbank.org) national accounts data

### 4. GDP per capita, PPP (current international $)

* This indicator provides per capita values for gross domestic product (GDP) expressed in current international dollars converted by purchasing power parity (PPP) conversion factor. GDP is the sum of gross value added by all resident producers in the country plus any product taxes and minus any subsidies not included in the value of the products. conversion factor is a spatial price deflator and currency converter that controls for price level differences between countries. Total population is a mid-year population based on the de facto definition of population, which counts all residents regardless of legal status or citizenship.

* Periodicity: Annua

* Source: [World Bank](https://data.worldbank.org) national accounts data


## R CODE

```{r}
install.packages("wbstats")
install.packages("WDI")
library(wbstats)
new_wb_cache <- wbcache() 
library(WDI)
new_wdi_cache <- WDIcache() 
```

```{r}
GDP_PCT_A<-WDI(indicator = c("NY.GDP.MKTP.KD.ZG"))
names(GDP_PCT_A)[1] <- "ISO"
names(GDP_PCT_A)[2] <- "COUNTRY"
names(GDP_PCT_A)[3] <- "VALUE"
names(GDP_PCT_A)[4] <- "YEAR"
write.csv(GDP_PCT_A,file="GDP_PCT_A.csv")
```


