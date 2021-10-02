# Airline-Fleet-Analysis
## Suggesting a fleet to an airline based on existing data on aircraft models
### Dataset
The dataset for this case study can be found [here](https://drive.google.com/drive/u/0/folders/1eiOpluriP46sVFcLy8z_xwn7hdFP3Z77).
### The CASE
For this case study, we are given two airlines:
- **Airline A**: Currently flying a large international network. Their flight operations are shown in the [Operations](https://docs.google.com/spreadsheets/d/1vNub8U467Q518X0RS7Sj3idj65ZIy07uaJW3fG9oMY8/edit?usp=sharing) table. Specifications for each aircraft in their fleet are listed in the [AC_characteristics](https://docs.google.com/spreadsheets/d/1KWaiaIu7pcuhvv9ftuDNOO0PIEEsHSdXoh3fKw-YkHE/edit?usp=sharing) table. They would like to know the following.
  1. The annual total cost by aircraft type (model).
  2. The aircraft model with the lowest **Cost per Seat per Km** flown. 
- **Airline B**: A startup airline considering operating on the routes as shown in the [City_pairs](https://docs.google.com/spreadsheets/d/1UEybm2VJaaG6V_VsOmTfuvwLm5QC43Kl8BSsIptrVC8/edit?usp=sharing) table. We need to suggest the right aircraft models suited for their operations.
### The IDEA
The solutions to **Airline A's** questions are pretty straightforward. It involves Dataframe operations like "Group By" and "Joins", followed by mathematical operations to calculate the desired metrics. One such metric is the **Cost per Seat per Km** flown by the aircraft. This metric shows that an airline bears the cost of flying for each seat in the aircraft, regardless of its occupancy.

However, for **Airline B**, the solution is an optimization between three factors: **Range of Aircraft**, **Passenger Demand**, **Cost of Flying**.
- The potential aircraft's range should cover the flight distance of that route.
- After filtering out the aircrafts from the previous step, we can find the no of flights required to meet the passenger demand.
- This would allow us to find the total number of seats using which, we can find the daily flying cost for that aircraft through the **Cost per Seat per Km** metric.
- Whichever aircraft has the lowest **Daily Flying Cost** will be desirable to fly that route. The same process is repeated for other routes as well.
