# Technical Specifications Document

## 1. Title Page
- **Project Name**: Airline Booking System
- **Version**: 
- **Date**: 
- **Author(s)**:
Joseph Ryan Caballero
Grace Pontanar
Iasaiah Alves
Jerrelyn Del Pilar
Lia Clemente

## 2. Table of Contents
1. [Introduction](#3-introduction)
2. [Overall Description](#4-overall-description)
3. [Visual Mockup Reference](#5-visual-mockup-reference)
4. [Features](#6-features)
5. [Functional Requirements](#7-functional-requirements)
6. [Non-Functional Requirements](#8-non-functional-requirements)
7. [Data Requirements](#9-data-requirements)
8. [External Interface Requirements](#10-external-interface-requirements)
9. [Glossary](#11-glossary)
10. [Appendices](#12-appendices)

## 3. Introduction
- **Purpose**: The Airline Booking System is designed to provide users with a seamless and efficient platform to search, compare, and book airline tickets. The system offers an intuitive interface with essential features such as flight search, booking confirmation, user dashboard, and payment processing.
- **Scope**: 
This application will allow users to:
Search for flights based on their preferences
Compare flight options
Make secure bookings
View upcoming flight details
Manage user profile and itinerary details

The application will not handle airline operations, baggage tracking, or real-time flight tracking.

- **Definitions, Acronyms, and Abbreviations**:
NoSQL: Non-relational database for flexible data storage
UI/UX: User Interface/User Experience
API: Application Programming Interface

- **References**:
Bootstrap documentation: https://getbootstrap.com/
JavaScript documentation: https://developer.mozilla.org/en-US/docs/Web/JavaScript

## 4. Overall Description
- **Product Perspective**: The Airline Booking System functions as a standalone web application for travelers to book flights. It integrates with third-party flight data sources for real-time flight availability.

- **Product Functions**: 
Flight search with filters
User authentication
Booking management
Payment processing
User dashboard with itinerary details
Mobile responsive system
Can easily manage booking using mobile phones or tablets
Has the option to download itinerary tickets

- **User Classes and Characteristics**:
Regular Users: Search and book flights
Admin Users: Manage system settings and promotions

- **Operating Environment**: 
Frontend: HTML, CSS, Bootstrap, JavaScript
Backend: NoSQL database
Network: Cloud-based deployment

- **Assumptions and Dependencies**: 
Requires internet connectivity
Payment gateway integration for secure transactions

## 5. Visual Mockup Reference
- **Link or Screenshot**: https://www.figma.com/design/lOiGafupfytA7AWHaIiGZJ/MCP-Side-Project-(Airline-Booking-System))?node-id=73-2&p=f&t=tVXqkQW97sn8SgdE-0

## 6. Features
- **Feature 1**: Responsive Navigation Bar

```js function responsiveNavigationBar(screenWidth, userClickEvent) {
    // Define breakpoints for different screen sizes
    const desktopBreakpoint = 
    const tabletBreakpoint = 
    const mobileBreakpoint = 
    // Check the screen width and adjust the navigation bar layout accordingly
    if (screenWidth >= desktopBreakpoint) {
        // Desktop layout
        setDesktopLayout();
    } else if (screenWidth >= tabletBreakpoint) {
        // Tablet layout
        setTabletLayout();
    } else {
        // Mobile layout
        setMobileLayout();}
    // Add event listeners for user interactions
    addUserClickListeners(userClickEvent);
    // Ensure fallback links in case of JavaScript failure
    ensureFallbackLinks();}
    function setDesktopLayout() {
        // Set the navigation bar layout for desktop screens
        showFullMenu();
        hideHamburgerMenu();}
    function setTabletLayout() {
        // Set the navigation bar layout for tablet screens
        showHamburgerMenu();
        hideFullMenu();}
    function setMobileLayout() {
        // Set the navigation bar layout for mobile screens
        showHamburgerMenu();
        hideFullMenu();}
    function showFullMenu() {
        // Display the full navigation menu
        let fullMenu = document.getElementById("fullMenu");
        fullMenu.style.display = "block";}
    function hideFullMenu() {
        // Hide the full navigation menu
        let fullMenu = document.getElementById("fullMenu");
        fullMenu.style.display = "none";}
    function showHamburgerMenu() {
        // Display the hamburger menu
        let hamburgerMenu = document.getElementById("hamburgerMenu");
        hamburgerMenu.style.display = "block";}
    function hideHamburgerMenu() {
        // Hide the hamburger menu
        let hamburgerMenu = document.getElementById("hamburgerMenu");
        hamburgerMenu.style.display = "none";}
    function addUserClickListeners(userClickEvent) {
        // Add event listeners for user clicks/taps
        let hamburgerMenu = document.getElementById("hamburgerMenu");
        hamburgerMenu.addEventListener("click", toggleMenu);
        // Handle other user click events if necessary
        handleUserClicks(userClickEvent);}
    function toggleMenu() {
        // Toggle the visibility of the navigation menu
        let fullMenu = document.getElementById("fullMenu");
        if (fullMenu.style.display === "none") {
            fullMenu.style.display = "block";
        } else {
            fullMenu.style.display = "none";
        }}
    function handleUserClicks(userClickEvent) {
        // Process user clicks/taps on navigation links
        let navLinks = document.querySelectorAll(".navLink");
        navLinks.forEach(link => {
            link.addEventListener("click", (event) => {
                // Handle the click event and navigate to the corresponding page
                navigateToPage(event.target.href);
            });
        });
    }
    function ensureFallbackLinks() {
        // Ensure navigation links are accessible in case of JavaScript failure
        let navLinks = document.querySelectorAll(".navLink");
        navLinks.forEach(link => {
            link.setAttribute("href", link.dataset.fallbackUrl);
        });
    }
    function navigateToPage(url) {
        // Navigate to the specified page
        window.location.href = url;} 
```

- **Feature 2**: Flight Search

```js function searchFlights(departureCity, destinationCity, departureDate, returnDate, numberOfPassengers) {
              // Validate input parameters
              if (!departureCity || !destinationCity || !departureDate || numberOfPassengers <= 0) {
              return "Invalid input parameters";
              }
              // Check if returnDate is provided for round-trip search
              let isRoundTrip = returnDate ? true : false;
              // Fetch available flights from the database or external API
              let availableFlights = fetchFlights(departureCity, destinationCity, departureDate, isRoundTrip ? returnDate : null, numberOfPassengers);
              // Check if any flights are available
              if (availableFlights.length > 0) {
              // Return the list of available flights
              return availableFlights;
              } else {
              // Return a message indicating no flights are available
              return "No flights available for the given criteria";
              }
              }
              function fetchFlights(departureCity, destinationCity, departureDate, returnDate, numberOfPassengers) {
              // This is a placeholder function to simulate fetching flights from a database or external API
              let flights = [
              {
                flightNumber:
                airline:
                departureCity:
                destinationCity: 
                departureDate:
                returnDate: 
                numberOfSeatsAvailable: 
              },
              {
                flightNumber:
                airline: 
                departureCity: 
                destinationCity: 
                departureDate:
                returnDate:
                numberOfSeatsAvailable: 
              }
              ];
              // Filter flights based on input criteria
              let filteredFlights = flights.filter(flight => {
              return flight.departureCity === departureCity &&
              flight.destinationCity === destinationCity &&
              flight.departureDate === departureDate &&
              (!returnDate || flight.returnDate === returnDate) &&
              flight.numberOfSeatsAvailable >= numberOfPassengers;
              });
              return filteredFlights;
              }
  ```


- **Feature 3**: User Authentication(Login/out)
```js
            function loginUser(email, password) {
            // Find the user by email
            let user = findUserByEmail(email);
            // Check if user exists and password matches
            if (user && checkPassword(password, user.hashedPassword)) {
            // Generate an authentication token for the user
            let token = generateAuthToken(user);
            return token;
            } else {
            // Return an error message if credentials are invalid
            return "Invalid credentials";
            }
            }
```
- **Feature 4**: Promotions and Offers
```js
          function displayPromotionsAndOffers(userPreferences, promotionalCampaigns) {
              // Validate input parameters
              if (!userPreferences || !promotionalCampaigns) {
                  return "Invalid input parameters";
              }
              // Fetch applicable promotions based on user preferences
              let applicablePromotions = fetchApplicablePromotions(userPreferences, promotionalCampaigns);
              // Apply discount rules to the promotions
              let discountedOffers = applyDiscountRules(applicablePromotions);
              // Remove expired promotions
              let validOffers = removeExpiredPromotions(discountedOffers);
              // Display the available offers
              displayOffers(validOffers);
          }
          function fetchApplicablePromotions(userPreferences, promotionalCampaigns) {
              // This is a placeholder function to simulate fetching promotions based on user preferences
              // In a real implementation, this function would query a promotions database or call an external promotions API
              // Sample data structure for promotional campaigns
              let promotions = [
                  {
                      promotionId: "PROMO1",
                      description: "10% off on all flights",
                      discount: 0.10,
                      expiryDate: "2025-03-15",
                      applicableTo: ["flights"]
                  }
              ];
              // Filter promotions based on user preferences
              let filteredPromotions = promotions.filter(promotion => {
                  return userPreferences.includes(promotion.applicableTo[0]);
              });
              return filteredPromotions;
          }
          function applyDiscountRules(promotions) {
              // Apply discount rules to the promotions
              promotions.forEach(promotion => {
                  // Apply discount logic if necessary
                  promotion.finalPrice = calculateDiscountedPrice(promotion);
              });
              return promotions;
          }
          function calculateDiscountedPrice(promotion) {
              // Placeholder function to calculate discounted price
              // In a real implementation, this would calculate the discount based on the original price and discount rate
              let originalPrice = 100; // Example original price
              let finalPrice = originalPrice - (originalPrice * promotion.discount);
              return finalPrice;
          }
          function removeExpiredPromotions(promotions) {
              // Remove promotions that have expired
              let currentDate = new Date("2025-02-28"); // Example current date
              let validPromotions = promotions.filter(promotion => {
                  return new Date(promotion.expiryDate) > currentDate;
              });
              return validPromotions;
          }
          function displayOffers(offers) {
              // Display the available offers
              offers.forEach(offer => {
                  console.log(`Promotion: ${offer.description}, Final Price: ${offer.finalPrice}`);
              });
          }
```
- **Feature 5**: Popular Destinations or Top Flights
```js
        function displayPopularDestinationsOrTopFlights(flightPopularityData) {
        // Validate input parameters
          if (!flightPopularityData) {
              // Fetch default popular destinations if data is unavailable
              let defaultPopularDestinations = fetchDefaultPopularDestinations();
              displayPopularFlights(defaultPopularDestinations);
              return;
          }
          // Display the list of popular flights
          displayPopularFlights();
      }
      function fetchDefaultPopularDestinations() {
          // This is a placeholder function to simulate fetching default popular destinations
          // Sample data structure for default popular destinations
          let defaultDestinations = [
                  { destination: },
                  { destination: },
                  { destination: }
          ];
          return defaultDestinations;
      }
      function displayPopularFlights(destinations) {
          // Display the list of popular flights
          destinations.forEach(destination => {
              console.log(`Destination: ${destination.destination}`);
          });
      }
```
- **Feature 6**: Flight Search Results
- **Feature 7**: Display details and Prices on Flight Results
- **Feature 8**: Filters and Sorting Options
- **Feature 9**: Flight Comparison
- **Feature 10**: Booking Confirmation
- **Feature 11**: Footer and Contact details
- **Feature 12**: Summary of the Booking
- **Feature 13**: Payment Information
- **Feature 14**: Download/Print Ticket
- **Feature 15**: Next Steps: Provide information on check-in time
- **Feature 16**: User Profile Page
- **Feature 17**: Search Feature in Profile Page
- **Feature 18**: Itinerary Details
- **Feature 19**: About Profile Page
- **Feature 20**: Upcoming Flights


## 7. Functional Requirements
### Use Cases
- **Use Case 1**:
  - **Title**: Booking a Flight
  - **Description**: This use case describes how a passenger books a flight through the airline booking system. The passenger selects a flight, enters personal details, makes a payment, and receives a booking confirmation.
  - **Actors**: 
    - Primary Actor: Passenger
    - Secondary Actors: Airline System, Payment Gateway
  - **Preconditions**:
    - The passenger has access to the airline booking system (website or mobile app).
    - The airline has available flights listed in the system.
    - The passenger has a valid payment method. 
  - **Postconditions**: 
    - The passenger successfully books a flight and receives a confirmation.
    - The airline system updates seat availability.
    - The payment is successfully processed.
  - **Main Flow**: 
    - The passenger logs into the airline booking system.
    - The passenger enters travel details (departure and destination, date, number of passengers).
    - The system displays available flights based on the entered criteria.
    - The passenger selects a preferred flight.
    - The passenger provides personal details (name, passport number, contact information).
    - The passenger selects a payment method and enters payment details.
    - The system processes the payment through the payment gateway.
    - Upon successful payment, the system generates a booking confirmation with ticket details.
    - The system displays the booking confirmation.
  - **Alternate Flows**: 
    - **No Flights Available**
      - If no flights match the search criteria, the system displays a message and suggests alternative dates or destinations.
    - **Payment Fails**
      - If the payment fails, the system notifies the passenger and provides an option to retry with a different payment method.
    - **Session Timeout**
      - If the passenger takes too long to complete the booking, the session expires, and the system prompts them to restart the process.

### System Features
**Feature 1: Responsive Navigation Bar**
  - **Description:** A top navigation bar that adjusts to different screen sizes and provides quick access to essential pages.
  - **Priority:** High
  - **Inputs:** User clicks/taps, screen resolution
  - **Processing:** Detects screen size and adjusts layout accordingly
  - **Outputs:** Visible navigation bar with accessible links
  - **Error Handling:** Ensure fallback links in case of JavaScript failure

**Feature 2: Flight Search**
  - **Description:** Allows users to search for flights by providing origin, destination, and travel dates.
  - **Priority:** High
  - **Inputs:** Departure city, destination city, departure date, return date (if applicable), number of passengers
  - **Processing:** Validates input, queries flight database, applies filters
  - **Outputs:** List of available flights
  - **Error Handling:** Display messages for invalid inputs or no available flights

**Feature 3: User Authentication (Login/Logout)**
  - **Description:** Secure login/logout functionality to access user-specific details
  - **Priority:** High
  - **Inputs:** Email/username, password
  - **Processing:** Validate credentials, authenticate user
  - **Outputs:** Successful login session or error message
  - **Error Handling:** Incorrect credentials, forgot password option

**Feature 4:** Promotions and Offers
  - **Description:** Displays discounts, special deals, and offers
  - **Priority:** Medium
  - **Inputs:** User preferences, promotional campaigns
  - **Processing:** Fetch and apply discount rules
  - **Outputs:** Display available offers
  - **Error Handling:** Ensure expired promotions are removed

**Feature 5: Popular Destinations or Top Flights**
  - **Description:** Shows trending flight routes and destinations
  - **Priority:** Medium
  - **Inputs:** Flight popularity data
  - **Processing:** Analyze and rank destinations
  - **Outputs:** List of popular flights
  - **Error Handling:** Display default popular destinations if data is unavailable

**Feature 6: Flight Search Results**
  - **Description:** Displays flight results after a user searches
  - **Priority:** High
  - **Inputs:** Search query from flight search feature
  - **Processing:** Fetch and filter available flights
  - **Outputs:** List of matching flights
  - **Error Handling:** Handle cases of no available flights

**Feature 7: Display Details and Prices on Flight Results**
  - **Description:** Provides detailed information on flight options, including price
  - **Priority:** High
  - **Inputs:** Selected flight details
  - **Processing:** Retrieve and display price and details
  - **Outputs:** Flight details including fare
  - **Error Handling:** Handle missing or incorrect pricing data

**Feature 8: Filters and Sorting Options**
  - **Description:** Allows users to refine search results
  - **Priority:** Medium
  - **Inputs:** User-selected filters (airline, price range, duration)
  - **Processing:** Apply filters and sort results
  - **Outputs:** Updated flight list
  - **Error Handling:** Ensure proper filter application

**Feature 9: Flight Comparison**
  - **Description:** Enables users to compare different flights
  - **Priority:** Medium
  - **Inputs:** Selected flights
  - **Processing:** Display side-by-side comparison
  - **Outputs:** Comparison table
  - **Error Handling:** Handle incomplete comparisons

**Feature 10: Booking Confirmation**
  - **Description:** Confirms successful booking
  - **Priority:** High
  - **Inputs:** User booking details
  - **Processing:** Store booking and generate confirmation
  - **Outputs:** Confirmation message
  - **Error Handling:** Handle payment or booking failures

**Feature 11: Footer and Contact Details**
  - **Description:** Provides contact information and quick links
  - **Priority:** Low
  - **Inputs:** Static content
  - **Processing:** Display footer content
  - **Outputs:** Visible footer
  - **Error Handling:** Ensure all links are functional

**Feature 12: Summary of the Booking**
  - **Description:** Displays a summary before finalizing booking
  - **Priority:** High
  - **Inputs:** Flight and passenger details
  - **Processing:** Fetch and format booking summary
  - **Outputs:** Booking summary display
  - **Error Handling:** Validate all details before proceeding

**Feature 13: Payment Information**
  - **Description:** Allows secure payment processing
  - **Priority:** High
  - **Inputs:** Payment details (card number, CVV, expiration)
  - **Processing:** Process payment through a secure gateway
  - **Outputs:** Payment success/failure notification
  - **Error Handling:** Handle invalid payments securely

**Feature 14: Download/Print Ticket**
  - **Description:** Allows users to download or print tickets
  - **Priority:** High
  - **Inputs:** Booking reference
  - **Processing:** Generate PDF/e-ticket
  -**Outputs:** Downloadable or printable ticket
  -**Error Handling:** Handle missing ticket data

**Feature 15: Next Steps: Provide Information on Check-in Time**
  - **Description:** Displays check-in details post-booking
  - **Priority:** Medium
  - **Inputs:** Flight details
  - **Processing:** Retrieve and display check-in info
  - **Outputs:** Check-in instructions
  - **Error Handling:** Provide generic check-in details if unavailable

**Feature 16: User Profile Page**
  - **Description:** Allows users to manage their accounts
  - **Priority:** Medium
  - **Inputs:** User details
  - **Processing:** Fetch and display profile data
  - **Outputs:** Profile dashboard
  - **Error Handling:** Handle missing profile data

**Feature 17: Search Feature in Profile Page**
  - **Description:** Enables users to search their past bookings
  - **Priority:** Low
  - **Inputs:** Search query
  - **Processing:** Retrieve matching records
  - **Outputs:** List of relevant results
  - **Error Handling:** Handle no results found

**Feature 18: Itinerary Details**
  - **Description:** Shows the user’s travel itinerary
  - **Priority:** High
  - **Inputs:** Booking details
  - **Processing:** Fetch and format itinerary
  - **Outputs:** Display itinerary
  - **Error Handling:** Handle missing or incorrect details

**Feature 19: About Profile Page**
  - **Description:** Provides an overview of profile functionalities
  - **Priority:** Low
  - **Inputs:** Static content
  - **Processing:** Display profile page details
  - **Outputs:** Informational text
  - **Error Handling:** Ensure content is accessible

**Feature 20: Upcoming Flights**
  - **Description:** Displays a list of future flights
  - **Priority:** High
  - **Inputs:** User bookings
  - **Processing:** Fetch upcoming flights
  - **Outputs**: Display upcoming trips
  - **Error Handling:** Handle cases of no upcoming flights

 

## 8. Non-Functional Requirements
- **Performance**: Describe performance requirements.
- **Security**: Outline security needs.
- **Usability**: Detail user interface and experience considerations.
- **Reliability**: Define reliability and availability requirements.
- **Supportability**: Specify maintenance and support requirements.

## 9. Data Requirements
- **Data Models**:
- **User**
  - userId (Primary Key)
  - firstName
  - lastName
  - email
  - password
  - mobileNumber
  - dateOfBirth
  - bookingHistory
  - address

- **Passenger**
  - passengerId(Primary Key)
  - userId(Foreign Key)
  - firstName
  - lastName
  - email
  - mobileNumber
  - baggageDetails
  - otherDetails
  - passengerType

- **Booking**
  - bookingId(Primary Key)
  - userId(Foreign Key)
  - flightId(Foreign Key)
  - passengerCount
  - bookingDate
  - flightType
  - totalPrice

- **Flight**
  - flightId(Primary Key)
  - airlineId(Foreign Key)
  - fromLocation
  - toLocation
  - departureDate
  - arrivalDate
  - seatsAvailable
  - price

- **Ticket**
  - ticketId(Primary Key)
  - bookingId(Foreign Key)
  - passengerId(Foreign Key)
  - seatNumber
  - ticketStatus
  - issueDate
  - ticketNumber

- **Payments**
  - paymentId(Primary Key)
  - bookingId(Foreign Key)
  - amount
  - paymentDate
  - paymentMethod
  - paymentStatus

- **Airline**
  - airlineId(Primary Key)
  - name
  - email
  - contactNumber

- **Database Requirements**:
  - User Collection (Stores user information and booking history)
  - Passenger Collection (Stores passenger details linked to a user)
  - Booking Collection (Stores booking details linked to a user and a flight)
  - Flight Collection (Stores flight information)
  - Ticket Collection (Stores ticket information for passengers)
  - Payments Collection (Stores payment details related to a booking)
  - Airline Collection (Stores airline company details)

- **Relationships:**

  - User → Booking (One-to-Many): One user can have multiple bookings.
  - Booking → Flight (Many-to-One): Many bookings can belong to a single flight.
  - Booking → Payment (One-to-One): Each booking has one payment record.
  - Airline → Flight (One-to-Many): One airline operates multiple flights.
  - Flight → Booking (One-to-Many): A flight can have multiple bookings.
  - User → Passenger (One-to-Many): A user can register multiple passengers.
  - Passenger → Ticket (One-to-One): Each ticket is assigned to a single passenger.
  - Booking → Ticket (One-to-Many): A booking can include multiple tickets for passengers.

- **Data Storage and Retrieval**: 
- **Data Retrieval Methods**
  - **Fetching a User’s Booking History**
    - { "userId": ObjectId("USER_ID") }
    - Perform a lookup to join with the `Booking` collection to retrieve detailed information.

  - **Retrieving Flight Details for a Specific Booking**
    - { "bookingId": ObjectId("BOOKING_ID") }
    - Use an aggregation pipeline to fetch the associated `flightId` details from the Flight collection.

  - **Fetching Passenger Information for a Booking**
    - { "bookingId": ObjectId("BOOKING_ID") }
    - Join with the `Ticket` collection and fetch associated `passengerId` data.

  - **Retrieving Payment Details for a Booking**
    - { "bookingId": ObjectId("BOOKING_ID") }
    - Directly fetch payment details using `bookingId` as a reference.

  - **Indexing for Performance Optimization**
    - Index on `email` for quick user lookups.
    - Compound index on `{flightId, departureDate}` for fast flight searches.
    - Index `bookingId` in `Payments` and `Tickets` for optimized queries.

  - This MongoDB schema ensures an efficient and scalable design while maintaining data integrity.
- **ERD**: https://app.diagrams.net/#G1v0GvuCPxpL7d9ioGvPHoyO4MvZZXl_TJ#%7B%22pageId%22%3A%22mNDo0j1P8SEVuHjTTdoJ%22%7D

## 10. External Interface Requirements
- **User Interfaces**: Provide sketches or descriptions of the user interface.
- **API Interfaces**: Briefly describe any APIs.
- **Hardware Interfaces**: Mention any required hardware interactions.
- **Software Interfaces**: Note any software interactions.

## 11. Glossary
- **Airline Booking System**: A web-based platform that allows users to search, compare, and book airline tickets.
- **Itinerary**: A document containing flight details, including departure/arrival times, layovers, and seat assignments.
- **Payment Gateway**: A secured service that processes online payments for booking tickets.
- **Cloud-Based Deployment**: Hosting the application on cloud servers for scalability and availability.
- **Flight Search Filters**: Options such as price range, duration, stops, and airlines to refine search results.
- **User Authentication**: The process of verifying a user’s identity through login credentials.
- **E-Ticket**: A digital version of a flight ticket sent to the user via email.

## 12. Appendices
- **Supporting Information**: Add any additional information here.
- **Revision History**: 
  - 20 Feb 2025 - Added a template and partial content for the TSD
  - 24 Feb 2025 - Added Visual Mockup Reference
  - 27 Feb 2025 - Added the Functional Requirements and Data Requirements
  - 28 Feb 2025 - Added Features and System Features


