# GE-TravelAgent-NoCode
# Multi-Agent Travel Planner System ✈️🌎

A highly structured, multi-agent AI system designed to orchestrate end-to-end travel planning. This project utilizes a **Main Orchestrator Agent** that delegates tasks to specialized **Subagents**, ensuring strict context-passing, budget adherence, and high-quality API-ready outputs.

## 🏗 Architecture (Orchestrator-Worker Pattern)
This system is designed to prevent the "customer service loop" (where AI repeatedly asks for the same information). 
1. **Phase 1: Information Gathering** (Purpose, Theme, Budget)
2. **Phase 2: Planning & Delegation** (Flights, Lodgings, Cars, Recommendations)
3. **Phase 3: Finalization & Execution** (Itinerary Doc, Calendar, Booking Fulfillment)

The Main Agent extracts context from the conversation and injects it into the `parameters` of the Subagent tools. The Subagents execute their specific tasks (using tools like SerpApi Google Flights or Google Travel) and return structured data.

## 🚀 How to Use
1. **Agent Platforms:** These prompts and JSON schemas are platform-agnostic. You can deploy them on Google Cloud Vertex AI, OpenAI Custom GPTs/Assistants API, LangChain, or AutoGen.
2. **Prompts:** Upload the markdown files in the `/prompts` directory as the "System Instructions" for each respective agent.
3. **Schemas:** Use the JSON files in the `/schemas` directory to define the "Function Calling" or "Tools" parameters for the Main Agent.
4. **External APIs:** For the Flight, Lodgings, Car Rental, and Recommendations agents, connect a Web Search Tool or specific APIs (like SerpApi Google Flights) to enable live data fetching.

## 🧠 Key Features
* **Strict Context Passing:** Subagents are forbidden from asking the user for information the Main Agent already knows.
* **Smart Budget Slicing:** The Budget Agent breaks the total budget into categories (e.g., Lodging Allocation, Flight Allocation).
* **Social Proof Validation:** Recommendations and Lodgings strictly require active Google Reviews (4.0+ stars).
* **Frictionless Handoffs:** Generates direct, pre-filled checkout links to Google Travel for fast booking without compromising PII security.

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
