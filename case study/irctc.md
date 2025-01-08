
1,20,000 concurrent sessions during peak time <br/>
30 million registered users <br/>
7,00,000 booking / day <br/>
3,00,00,000 enquiries/day <br/>
600 million revenue pre day <br/>


7000 trains <br/>
9000 stations <br/>
18000 train station pairs <br/>


https://prezi.com/p/bp5earcgnn1n/irctc-design/

Functional - Reservation, Search, Reporting 
Booking - 10/s
Search - 500/s
Constraint - Runs on Chrome > 80, IE 11 and above
Logical View - 
 a. Train Search - Keeps all the data in a matrix for quick search.Entire train schedule is in a cache matrix.
 b. Booking & Availability -  
   a. In-memory queue to buffer booking request. 120k at peak time.
   b. Divide queue by Train/class/date
   c. Max no of queue at peak no-of-train * no-of-class 
   d. Stop taking request if queue size goes beyond seat size + waiting list capacity. Rate limiting
 c. User, 
 d. Train Routes Planner 
Data - RDBMS, RDBMS, RDMS - Read Replicas, Partitioning 
Tables - Trains, TrainRoutes, Stations, 
Deployment - AKS, Azure APP Service, Managed Servers
Comunication - Sync vs ASync
Security - Login, Registration
Performance Modeling - 
