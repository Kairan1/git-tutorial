 
 
FINAL PROJECT PROPOSAL:
ECOBITE - A SURPLUS FOOD RESCUE WEB APPLICATION

BIIT 2305 SEM 2 2025/2026
SECTION 03  WEB APPLICATION DEVELOPMENT

GROUP MEMBERS: GROUP 5
NAME
MATRIC NO
MUAZ BIN MOHD AZWARZAMANI
2410355
MUHAMMAD AMMAR FAIZ BIN ABDUL RAHMAN
2411723
ABDULAZEEZ UMAR OPEYEMI
2320575
MUHAMMAD IMAN NURHAKIM BIN SAZALI
2417689
MUHAMMAD HAZIQ RAFIF BIN ROHAIZAM
2413307




LECTURER: DR. NAJHAN BIN MUHAMAD IBRAHIM

SUBMISSION DATE: 9TH JUNE 2026

1.0  Abstract
EcoBite is a web-based surplus food management system developed using Laravel 10 as part of a university project. The system aims to reduce food waste in university cafeterias by allowing vendors to sell leftover food at discounted prices to students. The application promotes sustainability, affordability, and efficient food distribution within campus communities.
The system is built using the Model-View-Controller (MVC) architecture and includes role-based authentication, a vendor management module, and a student browsing and reservation module. EcoBite provides a simple, interactive, and responsive platform that connects food vendors and students in real time.

2.0  Introduction
Food waste is a major global issue, particularly in institutional environments such as universities, where unsold food is commonly discarded at the end of each operating day. This results in unnecessary wastage of resources and represents a significant economic loss for cafeteria vendors.
EcoBite is designed to address this problem by providing a digital platform that enables vendors to post surplus food listings and allows students to browse and purchase discounted meals before they are discarded. By bridging the communication gap between vendors and students, EcoBite contributes to a more sustainable and cost-effective campus food ecosystem.

3.0  Problem Statement
University cafeterias currently face a number of challenges related to surplus food management. The key issues identified are as follows:
• No centralised system exists to manage surplus food efficiently at the end of each day.
• High volumes of food are wasted during closing hours due to unsold inventory.
• Vendors experience financial losses as a result of discarded meals.
• Students lack affordable meal options, particularly during peak academic periods.
• There is no reliable communication channel between vendors and students regarding food availability.
A centralised digital system is therefore required to address these interconnected problems and provide a practical solution for all stakeholders involved.



4.0  Objectives
The objectives of the EcoBite system are:
• To reduce food waste in campus cafeterias by enabling vendors to sell surplus food at discounted prices.
• To allow vendors to efficiently manage their surplus food listings through a dedicated dashboard.
• To provide students with affordable meal options and a convenient reservation mechanism.
• To develop a fully functional web application using the Laravel 10 framework.
• To demonstrate the practical application of the MVC (Model-View-Controller) architecture in a real-world scenario.

5.0  Project Scope
EcoBite is scoped to serve a campus-based environment. The following outlines the system boundaries:
5.1  User Roles
• Students – Browse available surplus food listings and make reservations.
• Vendors – Post, manage, and delete surplus food items.
5.2  System Features
• User authentication (registration, login, and logout).
• Vendor Dashboard – Add and delete food listings.
• Student Dashboard – View and reserve available food items.
• Surplus food listing display system.
• Reservation simulation system with unique pickup code generation.
• User profile management with profile picture upload.

6.0  System Requirements
6.1  Hardware Requirements
• Computer or laptop
• Minimum 4GB RAM
• Stable internet connection
6.2  Software Requirements
• Laravel 10 (Backend Framework)
• PHP 8.0 or higher
• Composer (Dependency Manager)
• Node.js and NPM
• MySQL (Database)
• Visual Studio Code (Code Editor)



7.0  System Design
7.1  MVC Architecture
EcoBite is built on the Model-View-Controller (MVC) architectural pattern as enforced by the Laravel 10 framework. This separation of concerns improves code maintainability, testability, and scalability.
Layer
Component
Responsibility
Model
User, SurplusItem
Handles data logic, Eloquent ORM relationships, and database interaction.
View
Blade Templates
Renders the user interface using Blade templating engine with Bootstrap 5.
Controller
AuthController, StudentController, VendorController
Processes HTTP requests, applies business logic, and returns appropriate responses.

 
7.2  Technology Stack
Technology
Purpose
Laravel 10
Backend MVC Framework
PHP 8+
Server-side scripting language
Blade Engine
Template rendering and view layer
Bootstrap 5
Responsive frontend UI components
MySQL
Relational database management
JavaScript
Basic client-side interactivity
Composer
PHP dependency manager
NPM
Node.js package manager

 
7.3  Database Design
The system uses a MySQL relational database with two primary tables: users and surplus_items.
7.3.1  users Table
Column
Type
Constraint
Description
id
BIGINT
Primary Key, Auto Increment
Unique identifier
name
VARCHAR(255)
NOT NULL
User's full name
username
VARCHAR(255)
UNIQUE, NOT NULL
User's unique username
email
VARCHAR(255)
UNIQUE, NOT NULL
User's email address
password
VARCHAR(255)
NOT NULL
Hashed password (bcrypt)
role
ENUM
student/vendor
Determines user type
profile_picture
VARCHAR(255)
NULLABLE
Path to profile image
timestamps
TIMESTAMP
-
created_at, updated_at

 
7.3.2  surplus_items Table
Column
Type
Constraint
Description
id
BIGINT
Primary Key, Auto Increment
Unique identifier
vendor_id
BIGINT
Foreign Key (users.id)
References the vendor
food_name
VARCHAR(255)
NOT NULL
Name of the food item
image
VARCHAR(255)
NULLABLE
Path to food image
original_price
DECIMAL(8,2)
NOT NULL
Original selling price (RM)
discounted_price
DECIMAL(8,2)
NOT NULL
Flash sale price (RM)
quantity
INTEGER
NOT NULL
Available units remaining
status
VARCHAR(255)
Default: Active
Active or Sold Out
timestamps
TIMESTAMP
-
created_at, updated_at

8.0  System Features
8.1  Authentication System
The authentication system was implemented using a custom AuthController with Laravel's built-in Auth facade. The following functionalities are included:
• User registration with role selection (Student or Vendor).
• Secure login using username and hashed password (bcrypt via Hash::make).
• Session-based authentication with session regeneration on login.
• Secure logout with session invalidation and CSRF token regeneration.
• Role-based redirection after login (students to Student Dashboard, vendors to Vendor Dashboard).
8.2  Student Module
The StudentController manages all student-facing functionality. Students are able to:
• View all available surplus food listings fetched dynamically from the database.
• Browse all registered vendors and view their individual profiles.
• Check discounted prices, remaining quantity, and estimated pickup time for each listing.
• Reserve a food item, which decrements the quantity and marks the item as Sold Out when quantity reaches zero.
• Receive a randomly generated 6-digit pickup code (e.g., ECO-482910) upon successful reservation.
• Manage their own profile including name, username, and profile picture upload.
8.3  Vendor Module
The VendorController handles all vendor-related operations. Vendors are able to:
• Post new surplus food listings including food name, original price, discounted price, quantity, and an optional image.
• View all their active listings displayed in a dedicated dashboard table.
• Delete any of their listings, which permanently removes the record from the database.
• Upload food item images stored in Laravel's public storage (storage/surplus_images).
8.4  Routing
All application routes are defined in web.php and are structured as follows:
• Public routes: Home, Login, Register.
• Protected routes (wrapped in auth middleware): Student Dashboard, Vendor Dashboard, Profile, Reservation, Vendor Listings.
• The success page is accessible publicly to display the reservation confirmation after redirect.

9.0  System Interface
This section presents the user interfaces developed for the EcoBite system. The interfaces were designed with simplicity, usability, and sustainability in mind. A green colour scheme was chosen to reflect the environmental goals of reducing food waste.
9.1  Home Page
The home page serves as the landing page of the EcoBite application. It introduces the platform and its core objective of reducing food waste by connecting vendors with students. The page features a hero section with a call-to-action for browsing meals and accessing the vendor portal, along with statistics showcasing meals rescued, students served, and food waste reduced.
Figure 1: EcoBite Home Page
9.2  Login Page
The login page allows registered users to securely access the system. Users enter their username and password to authenticate. The system validates credentials via the AuthController and redirects users to the appropriate dashboard based on their role (student or vendor).
Figure 2: User Login Page
9.3  Registration Page
The registration page allows new users to create an account. Users are required to provide their full name, username, email address, password, password confirmation, and account type (Student or Vendor). Validation is enforced server-side using Laravel's request validation rules.
Figure 3: User Registration Page
9.4  Student Dashboard
The Student Dashboard displays all available surplus food listings retrieved from the database. Each listing card shows the food name, vendor name, original price (struck through), discounted flash sale price, quantity remaining, and estimated pickup time. Students can reserve a meal directly from this page using the Reserve Now button.
Figure 4: Student Dashboard – Active Flash Sales
9.5  Reservation Success Page
After a student successfully reserves a food item, the system displays a confirmation page. The page shows the reserved food item name and a unique randomly generated 6-digit pickup code (prefixed with 'ECO-'). The student is instructed to present this code to the vendor upon collection.
Figure 5: Reservation Success Page with Pickup Code
9.6  Vendor Dashboard
The Vendor Dashboard enables vendors to manage their surplus food listings. The left panel contains a form for posting new surplus items (including image upload), while the right panel displays all current active listings in a table format with item details and a delete action for each row.
Figure 6: Vendor Dashboard – Manage Listings
9.7  Vendor Portal (Browse Vendors)
The Vendor Portal page allows students to browse all registered vendors on the platform. Each vendor card displays the vendor's name, operation time, and location. This feature provides students with an overview of all cafeteria vendors available on campus.
Figure 7: Vendor Portal – Browse All Vendors
9.8  Edit Profile Page
The Edit Profile page allows students to update their personal information including their full name, username, and profile picture. The email address and account type fields are displayed as read-only to prevent unauthorized modification. Profile pictures are stored in Laravel's public storage directory.
Figure 8: Edit Profile Page



10.0  Achievement of Assessment Requirements
The EcoBite system successfully satisfies all project assessment requirements as detailed in the table below:
 
Requirement
Implementation in EcoBite
Routes
Laravel routes were defined in web.php to manage all navigation between pages and system functions, including public and protected route groups using the auth middleware.
Controllers
Three controllers were implemented: AuthController (authentication), StudentController (student features including reservation and profile), and VendorController (listing management).
Views
Blade templates were developed for all user interfaces including the home page, login and registration pages, student dashboard, vendor dashboard, success page, profile page, and vendor portal.
Models
The User model (Authenticatable) and SurplusItem model were implemented with mass assignment protection via $fillable. The SurplusItem model defines a belongsTo relationship with the User model via vendor_id.
User Authentication
Complete authentication functionality was implemented including registration with role selection, username-based login, session management, CSRF protection, and role-based post-login redirection.
Use of Media
Text content, food item images (uploaded by vendors and stored via Laravel public storage), Bootstrap icons, and interactive UI components are incorporated throughout the application.
Design / Colour Scheme / Layout
A modern green sustainability-themed design using Bootstrap 5 was implemented. Responsive card layouts, gradient navigation bar, animated hero section, and consistent green colour branding were applied across all pages.
Navigation / Links
Navigation menus with dynamic auth-aware links, route-based internal navigation, and call-to-action buttons are integrated throughout the application for seamless user flow.

 



11.0  Testing
11.1  Functional Testing
The following functional test cases were conducted to verify that all core system features operate as expected:
 
No.
Test Case
Description
Expected Result
Status
1
User Registration
Register with valid name, username, email, password, and role.
Account created; redirected to appropriate dashboard.
PASS
2
User Login
Login with valid username and password.
Session created; redirected to appropriate dashboard.
PASS
3
Invalid Login
Login with incorrect credentials.
Error message displayed; user not authenticated.
PASS
4
Logout
Click logout from the navigation bar.
Session invalidated; redirected to home page.
PASS
5
Vendor – Post Item
Vendor submits the new surplus item form with valid data.
Item saved to database; appears in vendor dashboard table.
PASS
6
Vendor – Post with Image
Vendor uploads an image when posting a new item.
Image stored in storage/surplus_images; displayed in listing.
PASS
7
Vendor – Delete Item
Vendor clicks Delete on an existing listing.
Item removed from database; no longer visible in dashboard.
PASS
8
Student – View Listings
Students access the Student Dashboard.
All surplus items were fetched and displayed correctly with details.
PASS
9
Student – Reserve Item
Students click Reserve Now on an available item.
Quantity decremented; reservation code generated; success page shown.
PASS
10
Student – Reserve (Sold Out)
Student attempts to reserve an item with 0 quantity.
Error message displayed; reservation not processed.
PASS
11
Quantity Decrement
Item quantity decrements from 1 to 0 upon reservation.
Status changes to Sold Out automatically.
PASS
12
Profile Update
Student update their name, username, and upload a profile picture.
Profile updated in database; profile picture displayed.
PASS
13
Browse Vendors
Student navigates to the Vendor Portal page.
All registered vendors displayed with name and details.
PASS
14
Role-Based Redirect
Login as vendor vs student.
Vendor redirected to Vendor Dashboard; Student to Student Dashboard.
PASS

 
11.2  UI Testing
The following user interface testing was performed to ensure usability and responsiveness:
• Responsive layout was tested on desktop (1920px), laptop (1366px), and mobile (375px) screen sizes — all passed.
• Navigation links and route-based buttons were verified to direct users to the correct pages.
• Form inputs were tested with both valid and invalid data to confirm server-side validation responses.
• Flash messages (success and error alerts) were verified to appear and dismiss correctly.
• Bootstrap card layouts, tables, and buttons render correctly across Chrome, Firefox, and Edge browsers.



12.0  Limitations
While EcoBite successfully demonstrates a functional surplus food management system, several limitations are acknowledged:
• No payment gateway integration – the reservation system is simulated and does not process actual payments.
• No real-time updates – students must manually refresh the page to see updated listings; no WebSocket or polling is implemented.
• No notification system – vendors and students do not receive email or push notifications for new listings or reservations.
• No admin panel – there is no central administrator role to monitor overall system activity, manage users, or generate reports.
• Pickup code verification is manual – the generated code is not stored in the database and cannot be verified by vendors through the system.
• No search or filtering – students cannot search or filter listings by food type, price range, or vendor.



13.0  Future Enhancements
The following enhancements are proposed to improve EcoBite in future development iterations:
• Online payment gateway integration (e.g., FPX, Stripe) to process actual transactions.
• Real-time food inventory updates using Laravel Broadcasting and WebSockets (e.g., Pusher).
• QR code generation for pickup codes that vendors can scan using a mobile device to verify reservations.
• Email and push notification system to alert students of new listings and vendors of new reservations.
• Admin dashboard for system-wide monitoring, user management, and waste reduction analytics.
• Advanced search and filtering capabilities on the student dashboard (by vendor, price, food type).
• Mobile application (Android/iOS) for improved accessibility on smartphones.
• Rating and review system for vendors and food items.



14.0  Conclusion
EcoBite successfully demonstrates a functional web-based surplus food management system that addresses the problem of food waste in university cafeteria environments. The system achieves its primary objectives by connecting vendors and students through an interactive digital platform built on the Laravel 10 framework.
The application implements the MVC architectural pattern effectively, with clearly separated concerns across the model, view, and controller layers. Key features including role-based authentication, vendor listing management, student reservation functionality, and profile management have all been implemented and verified through functional testing.
Although the current version operates with a reservation simulation rather than a live payment system, EcoBite provides a strong and extensible foundation for a scalable real-world food waste management solution. With the proposed future enhancements, the system has the potential to be deployed as a fully operational campus sustainability platform.

