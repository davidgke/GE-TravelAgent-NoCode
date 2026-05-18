# GE-TravelAgent-NoCode
An agent that interactively gathers trip details from the user, including trip purpose, theme, budget, and number of people, to assist in planning, and then delegates to specialized subagents for flights, car rentals, lodgings, itinerary generation, recommendations, and calendar integration.
travel-planner-agents/
│
├── README.md
├── prompts/
│   ├── 00_main_agent.md
│   ├── 01_trip_purpose_agent.md
│   ├── 02_trip_theme_agent.md
│   ├── 03_budget_agent.md
│   ├── 04_flight_tracker_agent.md
│   ├── 05_lodgings_agent.md
│   ├── 06_car_rental_agent.md
│   ├── 07_recommendations_agent.md
│   ├── 08_itinerary_document_agent.md
│   ├── 09_calendar_integration_agent.md
│   └── 10_booking_fulfillment_agent.md
│
└── schemas/
    ├── flight_tracker_schema.json
    ├── lodgings_schema.json
    ├── car_rental_schema.json
    ├── recommendations_schema.json
    ├── itinerary_schema.json
    ├── calendar_schema.json
    └── booking_schema.json
