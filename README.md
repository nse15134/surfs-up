# Overview of the Analysis
 In this challenge, we will be working with Pandas and SQLAlchemy,  We want to be able to retrieve the data from the hawaii.sqllite database for the months of June and December.  We want to be able to determine if the surf and ice cream business is sustainable year-round.  We will do this by converting the temperatures for those months into a list and we can generate the entire list by date, and we can also create a summary statistics table.
 
 ## Results
 
 ### June Temperature
 
 ![June Temps](https://user-images.githubusercontent.com/98061420/160320967-aa633e3a-a19d-41e4-8368-26d1a51491ef.PNG)
 
 
 
 
 ### December Temperature
 
![December Temp](https://user-images.githubusercontent.com/98061420/160320980-e85237da-5784-4296-ba47-97878af9c935.PNG)

The data above represent June and December.  As we can see the Mean temperature for June is about 3 points higher than december. We can see June mean was about 73.94 and December was 71.04.  We can also note the the Max temp in june was two degrees warmer than December. We can note that the temperature did not go below 56 degrees. My recommendation would be to keep the business open all year long.  The metrics were fairly close from June to December.  


## Summary
As we can see from above, June is indeed warmer but not by too much.  It is our recommendation to keep the business open and I believe it will still do well.  The temperature changes are not drastic enough to cause and harm to the business. If we want to drill down into the details, we can run the following snippet of code to get the entire list and view the data at a much more granular level.

### June

session.query(Measurement.date, Measurement.tobs).filter(extract('month',Measurement.date)==6).all()

### December

session.query(Measurement.date, Measurement.tobs).filter(extract('month',Measurement.date)==12).all()
