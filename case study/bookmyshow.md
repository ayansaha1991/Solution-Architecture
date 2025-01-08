https://medium.com/@narengowda/bookmyshow-system-design-e268fefb56f5

<br/>
https://medium.com/@rishabh171192/system-design-book-my-show-online-booking-design-d71bb23be9be


Context - App Users, Theatre owners, Admins
Functional - Search movies, Pick one to see details, book seat, payment, ticket generation, reporting
Modules - 1. Vender Module, Movie & Theatre Search Module, Movie Catalog, Seat Booking, Payment, ticket generation
NFR - 
DB - RDBMS, RDBMS/Document, Elastic or Any Search, RDBMS, RDBMS, RDBMS
Entity - Country, City, Theatre, Shows, Movie, Seats 

## Vendor Movie upload Process - Performance Modeling
1. Fetch Price for the booking. - ~100ms
2. Query to book a seat. Update the seat status to a   temp-booked state. - ~ 1 second
4. If successful 
 - Complete the payment - ~5 second
 - Start a Cron to run in 5mins to check if payment is done. If not re-available the seats
5a. On Sucessful payment notification - Assign the seat.
5b. On Payment failure - Revert the seat to available.
6. Seat booked Notification => Ticket generation.

Arch-Style or Modularity boundary - 
a. Modular Monolith + Client-Server + Clean Arch 
b. Micro-Services + Client-Server + Clean Arch 
Language - Team's predominant general purpose language like Java, C#

APIs

Deployment - 
 Bare Metal -
 Managed VM -
 PAAS -
 Bare-Metal Container 
 Container Plaform PAAS
 Kubernetes - Managed vs Self-Managed

Performance Modeling -

Security - Authentication, API-Keys, TLS cert
Threat Modeling - 
Monitoring -