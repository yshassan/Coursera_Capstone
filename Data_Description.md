# Coursera Capstone, IBM Data Specialization  
## Course 9, Week 4 -- "Battle of the Neighborhoods"  
***  
### Part 2: A description of the data and how it will be used to solve the problem.

Firstly we will need to scrape postal location data of Birmingham and London to start with. Then retrieve the coresponding latitude & longittude coordinates of each postcode via geopy. If not then perhaps another website to scrape the information. 

Wikipedia tables will suffice for postcode data scrape. Their postal district tables will be used as a placeholder for a representive/central full postcode ('B1' as opposed to 'B1 1AA'). The Birmingham postal area (first 1-2 characters in a postcode) is just B while London is a much bigger city with 9 different postal districts (e.g. EC for East Central London). 

__Important Notice:__ Nominatim within geopy library will be the API to source geographical coordinates from. It is an open-source API which is volunteer run but have its limits on usage. The method that will be implemented uses geopy but despite some efforts to handle failed requests you may come across a time where geocoding won't work. In practice for regular geocoding, it is advisable to store/cache results or use a premium API for stakeholder needs.

We will then need to make calls to the Foursquare API to request venue data for each location. This will then need some preprocessing to extract venue data from the raw json file into something that can be analysed.

After cleaning the data, we can prepare to run K means clustering and form clusters of post codes in Birmingham/London. The output data will try to label each post code to clusters based on venue categories they offer. We then finally discuss findings from each cluster and how they distinguish from each other.
