In this project, I built an inventory dashboard to help the operation manager monitor the inventory trends and take prompt decisions. For example, For example: ask the team to review the purchase order when the projected inventory goes up, review the forecast/sale plan when slow-moving stock goes up, identify the key suppliers to focus on...


Tools used:
- Python
- Pandas
- Numpy
- Tableau


The raw data comes from 3 sources:
-Inventory file R0695: This file will have the data of current inventory (current stock on hand).
-Open PO: This file has the data on the incoming inventory (when and how much inventory will come).
-Forecast R0831: This file has the forecast of the items by months.


Obstacle:
-The forecast only has the data by month, while the incoming inventory can come on any day within the month. If we project the inventory per monthly bucket, it will be inaccurate. I.e., if the incoming inventory is at the beginning of the month, the actual inventory will be much higher than the projected one.


Solution:
-Using Pandas to manipulate the data to create the projected inventory by weekly bucket.
-The forecast was broken down from monthly to weekly. The incoming inventory date is rounded to the closest week date. The overdue purchase order will be projected to next week's inventory.
-The end-of-hand inventory is calculated and exported to a new file so that the historical data can also be reviewed.
   -End on hand = Current stock on hand + incoming purchase order - forecast


At the end, we will have a projected inventory by weekly bucket. The data from the previous weeks was also saved and visualised to monitor the trends.


The inventory data was visualised using Tableau to create an interactive dashboard.


Below are the screenshots of what it looks like:


-Overall dashboard: displays total inventory, top contributor, historical (red) and projected (blue) data, slow moving stock, stock by category, and so on.


![alt text](Output/tableau/image001.png)


-Additional information on hovering


![alt text](Output/tableau/image002.png)


-Master filtering


![alt text](Output/tableau/image003.png)


-Filter for connecting charts


![alt text](Output/tableau/image004.png)