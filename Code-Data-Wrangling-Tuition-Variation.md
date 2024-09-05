Data Wrangling
================

<center>
<h1>
**Set up**
</h1>
</center>

``` r
library(readxl)
library(dplyr)
library(viridis)
require(caret)
require(MASS)

# Most complete data use as a base
Base<- read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\CollegeDatEdited.xlsx")
BaseData<- as.data.frame(Base)


# Second data to be joined
Rank<-  read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\collegeRank.xlsx")
RankData<- as.data.frame(Rank)

# Change column name to match other data set
colnames(RankData)[which(names(RankData) == "College Name")] <- "University"

# Third data to be joined
CityData<- read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\schoolInfo.xlsx")

# Crime data to merge
CrimeData<- read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\Crime.xlsx")
```

<center>
<h1>
**Data Wrangling**
</h1>
</center>
<h2>
**Merge 1 and 2**
</h2>

``` r
# Merge 1 with Rank and Base


M1 <- merge(x=BaseData,y=RankData, 
      by.x=c("University","University"), 
      by.y=c("University","University"))


# Create new column in data frame that calculates that acceptance rate for the school, and a column that calculates total number of undergrads
M1$number_Undergrads<- M1$F.Undergrad+ M1$P.Undergrad
M1$Acceptance_rate<- (M1$Accept/M1$Apps)*100
```

``` r
# Merge 2 with City and M1
M2<- left_join(x= M1, y= CityData, by = "University")
```

``` r
# Export csv for Assignment checking submission and read that cvs back (requirement for assignment)

    # write.csv(M2, "C:\\Users\\roryq\\Downloads\\M2.csv",           row.names=FALSE)

M2.0<- read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\M2.xlsx")
```

``` r
# Remove excess/duplicate columns (by names)
M2.1 <- subset(M2.0, select = -c(P.Undergrad,F.Undergrad,Enroll,Top10perc,Top25perc,Personal,Apps,Accept,ranking,Terminal,PhD,primaryKey,Private,businessRepScore,engineeringRepScore,enrollment, state,Books))


# Or remove columns (by index)
M2.2 <- M2.1[-c(22,19,6,21,20)]
```

<h2>
**Merge 3**
</h2>

``` r
# Merge 3;  Crime and M2.2



# Change column name to match M3 for join
colnames(CrimeData)[which(names(CrimeData) == "NMCNTY")] <- "city"
colnames(CrimeData)[which(names(CrimeData) == "Overall Rank")] <- "City Rank"



# Merge 3
M3<- inner_join(x= M2.2, y= CrimeData, by = "city")


# Remove excess/duplicate columns (by name)
M3.1 <- subset(M3, select = -c(NtnlPrkCnt,FIPS,LSTATE))


#  Or remove columns (by index)
M3.2 <- M3.1[-c(35,37:45,19,31,20,18,27,30,22,25,28,29,26,47)]
```

``` r
# Export csv for Assignment checking submission and read that cvs back (requirement for assignment)

  #write.csv(M3.2, "C:\\Users\\roryq\\Downloads\\M3.2.csv",        row.names=FALSE)

obs_60_final<- read_excel("C:\\Users\\roryq\\Downloads\\Stat 1223\\M3.2.xlsx")

# Change column names
colnames(obs_60_final)[which(names(obs_60_final) == "2016 Crime Rate")] <- "Crime_Rate"
colnames(obs_60_final)[which(names(obs_60_final) == "2022 Median Income")] <- "Median_Income"
colnames(obs_60_final)[which(names(obs_60_final) == "Cost of Living")] <- "Cost_of_Living"
```

``` r
# convert crime rate to be adjusted by 1000
vec<- c(18,24,16,19,21,19,13,48,36,31,42,21,27,15,16,42,52,37,8,44,33,33,50,3,34,13,18,21,50,24,10,21,45,29/22,26,15,11,42,24,15,36,31,15,8, 0, 42,22, 68,32,51,16,32,51,35,13,51,19,27, NA,NA)

vec2<-numeric()
for(i in vec){
  vec2<- c(vec2,i/1000)
}

obs_60_final$Crime.Rate<-vec2
```

<h2>
**Final Data Frame**
</h2>

``` r
# Display number of observations and column names for final dataset to model
colnames(obs_60_final)
```

    ##  [1] "University"           "city"                 "Rank"                
    ##  [4] "institutionalControl" "Tuition"              "S.F.Ratio"           
    ##  [7] "perc.alumni"          "Expend"               "Grad.Rate"           
    ## [10] "number_Undergrads"    "Acceptance_rate"      "Crime_Rate"          
    ## [13] "Unemployment"         "Cost_of_Living"       "Median_Income"       
    ## [16] "AVG_C_two_I"          "1p1c"                 "Diversity_Rank_Race" 
    ## [19] "Crime.Rate"

``` r
nrow(obs_60_final)
```

    ## [1] 60
