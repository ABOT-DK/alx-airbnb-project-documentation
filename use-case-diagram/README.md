```mermaid
%% Airbnb Clone - Use Case Diagram (Vertical Layout)

graph TB

%% Guests
Guest[Guest]
Guest --> Register[Register]
Guest --> Login[Login]
Guest --> Search[Search Properties]
Guest --> ViewListing[View Listing]
Guest --> Book[Book Property]
Guest --> Payment[Make Payment]
Guest --> CancelBooking[Cancel Booking]
Guest --> Review[Leave Review]

%% Hosts
Host[Host]
Host --> Register
Host --> Login
Host --> ListProperty[List Property]
Host --> EditListing[Edit Listing]
Host --> ManageAvailability[Manage Availability]
Host --> AcceptBooking[Accept/Reject Booking]
Host --> Payout[Receive Payout]
Host --> Review

%% Admin
Admin[Admin]
Admin --> ManageUsers[Manage Users]
Admin --> ApproveListings[Approve Listings]
Admin --> ViewDashboard[View Dashboard]
Admin --> IssueRefund[Issue Refund]

%% Payment Gateway (external system)
PaymentGateway["Payment Gateway"]
Payment --> PaymentGateway
Payout --> PaymentGateway
IssueRefund --> PaymentGateway

