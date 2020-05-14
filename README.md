# Ebay-Car
Exploring Ebay Car Sales Data

###  Used cars database


![ebay](https://github.com/sandramalaquias/Ebay-Car/blob/master/ebay.png)

In this guided project, we'll work with a dataset of used cars from eBay Kleinanzeigen, a classifieds section of the German eBay website.

The dataset was originally scraped and uploaded to Kaggle. Dataquest few modifications from the original dataset that was uploaded to [Kaggle](https://www.kaggle.com/orgesleka/used-cars-database/data)


* Sampled 50,000 data points from the full dataset, to ensure your code runs quickly 
* Dirtied the dataset a bit to more closely resemble what you would expect from a scraped dataset (the version uploaded to Kaggle was cleaned to be easier to work with)

The data dictionary provided with data is as follows:

*   dateCrawled - When this ad was first crawled. All field-values are taken from this date.
*   name - Name of the car.
*   seller - Whether the seller is private or a dealer.
*   offerType - The type of listing
*   price - The price on the ad to sell the car.
*   abtest - Whether the listing is included in an A/B test.
*   vehicleType - The vehicle Type.
*   yearOfRegistration - The year in which the car was first registered.
*   gearbox - The transmission type.
*   powerPS - The power of the car in PS.
*   model - The car model name.
*   kilometer - How many kilometers the car has driven.
*   monthOfRegistration - The month in which the car was first registered.
*   fuelType - What type of fuel the car uses.
*   brand - The brand of the car.
*   notRepairedDamage - If the car has a damage which is not yet repaired.
*   dateCreated - The date on which the eBay listing was created.
*   nrOfPictures - The number of pictures in the ad.
*   postalCode - The postal code for the location of the vehicle.
*   lastSeenOnline - When the crawler saw this ad last online.

The aim of this project are:
* to clean the data and analyze the included used car listings. You'll also become familiar with Pandas library. 
* to get some notes about the files


## Additional Resources

* Chardet - using chardet to identify the correct encoding for the file. This is a bit hard
* Pandas
* Numpy
* Datetime

## Notes
This file has 50000 rows and 20 columns. The dtypes are ojects (like strings) and integer (int64). 
Some columns are no filled at all (all objetcs dtypes) but no more than 20%:

* vehicletype - 44905 (5,095 missing values)
* gearbox - 47320 (2,680 missing values)
* model - 47242 (2,758 missing values)
* fuelType - 45518 (4,482 missing values)
* notRepairedDamege - 40171 (9,829 missing values)

### About contents

* Seller: Only have 'gewerblich' = comercial and privat = private. #more than 99% are private seller
* offer_type: Only have 'Angebot' = offer and gesuch = request. #more than 99% are offer
* gearbox: three contents are available: automatic (about 21%), manual (about 74%) and null values (about 5.36%)
* not_repaired_damage: three contents are available: yes (70%)/ no (10%)/ null (20%)
* For abtest: not clear between test and control

The offer is higher for cars with more than 100.000km, different what occurs in Brazil.
There are 2357 differents values in price colum. 

There are zeros values and values less than 1000 that doesn't look right. But, Searching in the internet I find out there are some car that are free or with a very low price due "the owners give them away because it's cheaper then to take them to the scrap yard where you usually pay a fee".

Let's see the higher values. Again, searching in the internet I find out that more expensive new car is Mercedes-Benz 300 SLR - W196S - US $43,500,000 and Mercedes McLaren SLR 999 Red Gold Dream - US $10,000,000. 

Therefore, prices greather than US $10,000,000 are likely wrong and removed.

 ## Information regarding dates
 To see the distribuition curve maybe interesting to put it in a histogram.
 
 
### Info to Date crawled
Bellow is possible to see the quantity of post by date crawled, classified from date with higher number posts to 
date with fewest posts.
* This date_crawled is for one month only and maybe for the last date is not correct (or this is a outlier)
* The higher is 2016-04-03 with 1934 posts (correspoding a 3,87% of the total posts) 
* The fewest is 2016-04-07 with 71 posts (correspoding a 0,14% of the total posts) 
* The range is from 2016-03-05 to 2016-04-07

### Info to date seen
Bellow is possible to see the quantity of post by date seen, classified from date with higher number posts to 
date with fewest posts.

This date_seen is for one month only and maybe for the last date is not correct (or this is a outlier)

* The higher is 2016-04-06 with 11048 posts (correspoding a 22,1% of the total posts) 
* The fewest is 2016-03-05 with 54 posts (correspoding a 0,11% of the total posts) 
* The range is from 2016-03-05 to 2016-04-07

### Info to date created
Bellow is possible to see the quantity of post by date created, classified from date with higher number posts to 
date with fewest posts.

* The higher is 2016-04-03 with 1946 posts created (correspoding a 3,891% of the total posts) 
* The fewest is 2015_12_30 with 1 posts (correspoding a 0,02% of the total posts) 
* The range is from 2015-06-11 to 2016-04-07

### Info to month of registration

Maybe has no correct values due month = 0. I'm going to desconsiderate the month equal zero.
To see this distribuition curve could use the bar chart due a low densitive (only 12 month)

* The higher is march with 5069 posts created  
* The fewest is febreary with 3007 posts  
* The range is from january to december  

## Results
**More offer**
* Brand: Volksvagen
* Offer: 10187

**Less offer**
* Brand: Lada
* Offer: 29

**High Price**
* Brand: sonstige_autos
* Offer: 526
* Price: 10000000.00

**Less Price**
* Brand: Volkswagen
* Offer: 10187
* Price: 0.00



