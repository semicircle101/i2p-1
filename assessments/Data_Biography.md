# Data Biography

## Student Number: 20158115

---

### 1. Who collected the data?

_The data comes from Airbnb url by online web-scraping from and is subsequently converted into structured data form (csv file in this case), by data engineers._

---

### 2. Why did they collect it?

_There can be multiple use cases for the collected data, e.g. predicting the price of Airbnb properties, monitoring the performance of Airbnb offerings, studying the pricing trend of local housing market, and tracking ownership portfolio and pricing strategy of individual owners (super host vs. ordinary host)._

---

### 3. How was it collected?

_The data is automatically collected around specified dates (e.g. 2020-08-24 through 2020-08-28) and transformed to "property-date" level. It is further transformed to "property" and "host" level respectively. For example, variables such as "listing_url", "latitude", "longitude" "neighbourhood_overview" are used to describe property characteristics whereas variables such as "host_name", "host_response_rate" are providing more information regarding the host of the property. Both property-level and host-level information are further consolidated into one combined dataset as displayed._

---

### 4. What useful information does it contain?


_Aside from most important feature “price”, many more other variables are included in the dataset: 
(1)	Location: neighbourhood, latitude, longitude
(2)	Property: property type, room type, total number of accommodates, number of bedrooms, number of beds, amenityes. 
(3)	Availability: instantly bookable, minimum and maximum nights, current availability, whether calendar has updated, and number of nights available in 30, 60, 90, or 365 days. 
(4)	Historic feedback: review score, review scores on cleanliness/checkin/communicateon/value, number of reviews, first and last review. 
(5) Host information: super host or not, host since, host response rate and time, host’s total listing count (1 host may offer multiple listings)._

---

### 5. What useful information is it missing?

_There are total of 74 variables, 21 variables are missing more than 10% of data. Among the 21, some of them could be very useful for later analysis, for example: host response rate (49% missing), host acceptance rate (30% missing), review scores for cleanliness, location, checkin, communication, value (30% missing)._

---

### 6. To what extent is the data 'complete'?

_Fortunately, key variable “Price” has full availability without missing data.  
(1) Location: “latitude” and “longitude” information are almost fully available. Neighbourhood variables such as “neighbourhood, host_neighbourhood” are not as good with 36% and 24% missing. However, the “neighbourhood_cleansed” variable fill in the information with 100% available, covering 34 neighbourhoods.
(2) Property: “property_type, room_type, accommodates, beds, amenities” are fully available; “bedrooms” is slightly missing for 6%. Variable “bathrooms” is 100% missing. However, number of bathrooms can be easily derived by extracting the first number from “bathrooms_text” field, which gets almost none missing. 
(3) Availability: only “calendar_updated” is missing for 100%, yet all other more meaningful and important variables of this categories are fully available, such as “has_availability”, “maximum_nights”, “minimum_nights”, “instant_bookable”. 
(4) Historic feedback: among all the review variables, only “number_of_reviews” data is all available to use. Other specific review score for cleanliness, checkin, communication, location are missing at 30% across the board. However, this might not be a data quality issue. The missing data could be due to lack of reviews for new Airbnb listings, since 27% of the data are without “first_review” and “last_review” for similar reason of “new listing”.  
(5) Host information: “host_is_superhost”, “host_listings_count”, “host_since”, “host_location” are good to use. 
super host or not, host since, host response rate and time, host’s total listing count (1 host may offer multiple listings). Yet “host_response_time”, “host_response_rate”, “host_acceptance_rate” are missing from 30-50%. This may come from Airbnb customers’ reluctance to report the information. _

---

### 7. What kinds of analysis would this support?

_Looking at “neighbourhood” variable, it seems all the data comes from United Kingdom and a good amount of the neighbourhoods locate around Greater London area. We can use “latitude and longitude” information to create a measurement of distance from each property to London city center. This can provide more detailed information than dummies variables created for each of the 34 neighbourhoods, since location usually is the most important factor affecting property value and prices. A spatial data analysis can be done to check the price variations by location.
(1)	With property feature variables, we can study the supply of different property types in UK/Greater London area. Do they vary by neighbourhoods?
(2)	 Only 16% of the listings are offered by “Super Host”. We can analyze the data to see what makes a Super Host, do 16% super host differ with 84% ordinary host in property locations, prices, property and room types or instant bookings? _

---

### 8. What kinds of analysis would it _not_ support?

_There should be peaks and drops in the demand and hence the price. We would like to analyse the trend of the price throughout the time and see if there are any seasonal patterns associated with demands or supplies across months of the year. We can further do a more granular analysis to see if the price fluctuates throughout weekdays of a week. But in this dataset, the data only covers days from 2020-08-26 to 2020-08-28. Unfortunately, we did not study any time-related pattern given the extremely limited time frame.

We are also interested in exploring the living experience for each property, using different review scores. For example, the review score of “cleanliness” will help Airbnb to do cleaning quality control on of each property, and review score of “accuracy” evaluates if the listing description and pictures reflect the true condition of the rooms and property. Yet the high missing portion of the review scores restrained us to do further exploration._

---

### 9. Which of the uses presented in Q.7 and Q.8 are _ethical_?

_The first and foremost concern around data ethics is privacy concern, whether or not the individual’s privacy has been violated during the data generation and usage. In this case, the data is web-scraped from Airbnb open-source platform for public. In order to connect hosts and guests, the platform must display the necessary information about the listings such as neighbourhood, property type, number of rooms, price, general availability dates, amenities available. Airbnb also provides photos of units with basic descriptions adding to the display. Any user who signed up an Airbnb account and will be able to view the information. Thus, all information scraped from Airbnb website are fully available to general public to facilitate users finalizing their rental decisions and to ensure the rental safety and comfort. The data scraped here are coming from Airbnb users’ (guests’) public available web pages, instead of owners’ (entirely or partially) confidential profiles such as LinkedIn profiles. Therefore, scraping these publicly available and commercially essential data should not involve into “privacy breaches”.   
Secondly, regarding the analytic purpose of this data. In our analytics, we would like to mainly use data to (1) track price trends and subsequently predict the property-level price to make sure Airbnb hosts did not set the price off-track, and (2) conduct quality control of Airbnb hosts by analyzing the guests’ reviews, which aims to provide better hosting experience to guests. Thus, we do not aim to use the data to manipulate customers and pursue extra commercial profits (different from cases around Facebook and Amazon). But rather, Airbnb users are main beneficiaries of this data use and analytics for better service provided and monitored as the result, since unlike other e-commerce or social media platforms, hosting and rental business is more determined by users’ experience in reality and guaranteed safety should be a top concern for Airbnb thanks to the data support._

 
