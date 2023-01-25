# API Documentation for hall Booking

### following documents gives information about all API request and response with sample data and methods are used

1.  <mark>Create Room </mark>

    1. `POST` - http://localhost:4000/createRoom
    2. sample POST request
       ```
       {
        "room_type": "premium",
        "amenities": "Air Conditioning, Free Wi-Fi, medium Podium",
        "seats": 150,
        "price_per_hour": 2000
        }
       ```
    3. Sample BODY Response
       ```
           {
                "message": "Room is created successfully"
            }
       ```
2.  <mark>Book Rooms </mark>

    1. `POST` - http://localhost:4000/bookRoom
    2. Sample POST request

       ```
           {
            "customer_Name": "Deepak",
            "room_type": "premium",
            "date": "2023-01-13",
            "starting_time": "08:10 AM",
            "ending_time": "12:10 PM",
            "status": "Confirmed"
            }
       ```

       3.Sample BODY response

       1. If room booked successfully

       ```
          {
             "message": "Room is booked successfully"
           }
       ```

       2. If time slot is already booked by other customer response given below

       ```
           {
            "message": "the room is not available in this time slot, please select the different time slot"
            }
       ```

3.  <mark>List All Room </mark>

    1. `GET` - http://localhost:4000/listRooms
    2. No request needed
    3. Sample BODY Response

    ```

    [
        {
            "room_type": "premium",
            "room_id": "P000",
            "amenities": "Air Conditioning, Free Wi-Fi, medium Podium",
            "seats": 150,
            "price_per_hour": 2000
        },
        {
            "room_type": "Super-premium",
            "room_id": "P001",
            "amenities": "Air Conditioning, AV facilities, Free Wi-Fi, Large Podium",
            "seats": 300,
            "price_per_hour": 5000
        },
        {
            "room_type": "premium",
            "room_id": "P002",
            "amenities": "Air Conditioning, Free Wi-Fi, medium Podium",
            "seats": 150,
            "price_per_hour": 2000
        }
    ]
    ```

4.  <mark>List Booked Details </mark>
    1. `GET` - http://localhost:4000/bookedDetails
    2. No request needed
    3. Sample BODY response
    ```
    [
        {
            "room_id": "P000",
            "room_type": "premium",
            "customer_name": "Gokul Krishnan",
            "date": "2023-01-13T00:00:00.000Z",
            "starting_time": "08:00 AM",
            "ending_time": "12:10 PM",
            "status": "Confirmed"
        },
        {
            "room_id": "P001",
            "room_type": "Super-premium",
            "customer_name": "Gokulnath",
            "date": "2023-01-13T00:00:00.000Z",
            "starting_time": "11:00 AM",
            "ending_time": "03:00 PM",
            "status": "Confirmed"
        },
        {
            "room_type": "premium",
            "starting_time": "08:10 AM",
            "ending_time": "12:10 PM",
            "status": "Confirmed"
        }
    ]
    ```

5.  <mark>List All Customer Details </mark>
    1. `GET` - http://localhost:4000/customerDetails
    2. No request needed
    3. Sample BODY response
    ```
    [
        {
            "customer_name": "Gokul Krishnan",
            "room_type": "premium",
            "room_id": "P000",
            "date": "2023-01-13T00:00:00.000Z",
            "starting_time": "08:00 AM",
            "ending_time": "12:10 PM"
        },
        {
            "customer_name": "Gokulnath",
            "room_type": "Super-premium",
            "room_id": "P001",
            "date": "2023-01-13T00:00:00.000Z",
            "starting_time": "11:00 AM",
            "ending_time": "03:00 PM"
        }
    ]
    ```