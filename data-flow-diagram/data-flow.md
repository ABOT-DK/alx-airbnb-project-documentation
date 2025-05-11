```mermaid
flowchart TD
  %% External Entities
  User([User])
  PaymentGateway([Payment Gateway])

  %% Processes
  P1[Register/Login]
  P2[Manage Properties]
  P3[Search & View Listings]
  P4[Create Booking]
  P5[Process Payment]
  P6[Leave Review]

  %% Data Stores
  D1[(Users DB)]
  D2[(Properties DB)]
  D3[(Bookings DB)]
  D4[(Payments DB)]
  D5[(Reviews DB)]

  %% Data Flow: Registration/Login
  User -->|Registration Data| P1
  P1 -->|New User Record| D1
  P1 -->|Auth Success| User

  %% Data Flow: Property Management
  User -->|Listing Info| P2
  P2 -->|Save/Update Property| D2

  %% Data Flow: Search/View
  User -->|Search Criteria| P3
  P3 -->|Query Results| D2
  P3 -->|Listing Details| User

  %% Data Flow: Booking
  User -->|Booking Request| P4
  P4 -->|Check Availability| D2
  P4 -->|Create Booking| D3
  P4 -->|Send to Payment| P5

  %% Data Flow: Payment
  P5 -->|Payment Info| PaymentGateway
  PaymentGateway -->|Success/Failure| P5
  P5 -->|Record Transaction| D4
  P5 -->|Confirmation| User

  %% Data Flow: Review
  User -->|Review Info| P6
  P6 -->|Save Review| D5
