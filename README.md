# hotel_booking_and_reservation_api


## Summary:
1. There is a pre-build structure for Hotels/Apartments (could be changed or extended). Database is prefilled with information - **db.sqlite3**.
    - superuser
        - username: **admin**
        - password: **admin**

2. We can **block days** ( make reservations ) for each **Apartment** or **HotelRoom**.

3. There are available Apartments and Hotels based on:
	- **available days** (date range ex.: "from 2021-12-09 to 2021-12-12")
            - Apartments do not have any blocked day inside the range
            - Hotel has at least 1 Hotel Room available from any of the HotelRoomTypes
     - **max_price** (100)

## Initial Project setup
    git clone https://github.com/madjanorjedidiah/hotel_booking_and_reservation_api.git
    python -m venv venv
    pip install -r requirements.txt
    python manage.py runserver


## Request example:

http://localhost:8000/api/v1/units/?max_price=100&check_in=2021-12-09&check_out=2021-12-12


## Response example:

    {
        "items": [
            {
                "listing_type": "Apartment",
                "title": "Luxurious Studio",
                "country": "UK",
                "city": "London",
                "price": "40"

            },
            {
                "listing_type": "Hotel",
                "title": "Hotel Lux 3***",
                "country": "BG",
                "city": "Sofia",
                "price": "60" # This the price of the first Hotel Room Type with a Room without blocked days in the range

            },
            {
                "listing_type": "Apartment",
                "title": "Excellent 2 Bed Apartment Near Tower Bridge",
                "country": "UK",
                "city": "London",
                "price": "90"
            },
        ]
    }
