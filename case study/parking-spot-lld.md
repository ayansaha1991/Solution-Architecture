# Design a parking lot 

Requirements: 

1. Multiple floot as a Garage
2. Different types of Parking spot. Small, mediam, big, electric
3. Different types of vehicle. Bike, Card, Buses
3. Assign a vehicle to a spot.
4. See if parking is full
5. Calculate payment.
6. Generate Ticket for Payment calculation

API :
POST  {parkingLotId}/reserve-spot
{
    "parkingLotId": "",
    "vehicleType": "" 
}

GET  {parkingLotId}/available-spots
{
    "parkingLotId":
    "vehicleType": //optional
    "floor": "" // optional
}

POST /generate-tickets
{

}

Entity:

1. ParkingLot 
- id
- name
- adress: 

2. Floor
- id 
- parkingLotId
- floorNo

3. ParkingSpot
- id
- parkingLotId
- parkingSpotId
- spotName
- size: ParkingLotSize

4. ParkingSpotSize
- Big
- Small
- Medium
- Electric

5. Vehicle
- name : 
- size: VehicleSize
- number:

6. VehicleSize

7. Parking
- id: 
- spot: 
- entryTime:
- exitTime
- ticketNo:
- vehicleId

8. Ticket.
- id: 
- parkingId 
- startTime: 
- spot
- payment 

9. Payment
10. ParkingFeeType <- Hourly, Flat
11. ParkingFee 
- type: 
- charge: 