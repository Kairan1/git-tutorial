EcoBite: Surplus Food Rescue Web Application

BIIT 2305 Semester 2, 2025/2026

Section 03 | Web Application Development

Group 5

EcoBite is a web-based surplus food management system built using Laravel 10. The application aims to reduce food waste in university cafeterias by bridging the gap between vendors with excess food and students looking for affordable, discounted meals.
👥 Project Team
Name	Matric No
MUAZ BIN MOHD AZWARZAMANI	2410355
MUHAMMAD AMMAR FAIZ BIN ABDUL RAHMAN	2411723
ABDULAZEEZ UMAR OPEYEMI	2320575
MUHAMMAD IMAN NURHAKIM BIN SAZALI	2417689
MUHAMMAD HAZIQ RAFIF BIN ROHAIZAM	2413307
Lecturer: Dr. Najhan Bin Muhamad Ibrahim

Submission Date: 9th June 2026
1.0 Abstract

EcoBite is a web-based surplus food management system developed using Laravel 10. The system aims to reduce food waste in university cafeterias by allowing vendors to sell leftover food at discounted prices to students. The application promotes sustainability, affordability, and efficient food distribution within campus communities.2.0 Introduction

Food waste is a major global issue, particularly in institutional environments such as universities. EcoBite provides a digital platform that enables vendors to post surplus food listings and allows students to browse and purchase discounted meals before they are discarded, contributing to a more sustainable campus food ecosystem.3.0 Problem Statement
No centralised system exists to manage surplus food efficiently.
High volumes of food are wasted during closing hours.
Vendors experience financial losses from discarded meals.
Students lack affordable meal options.
Lack of a reliable communication channel between vendors and students.
4.0 Objectives
Reduce campus food waste.
Provide vendors with a dedicated dashboard to manage surplus items.
Offer students affordable meal options and a convenient reservation system.
Implement MVC architecture using the Laravel 10 framework.
5.0 Project Scope5.1 User Roles
Students: Browse available surplus food listings and make reservations.
Vendors: Post, manage, and delete surplus food items.
5.2 System Features
User authentication (Registration, Login, Logout).
Vendor Dashboard: Add and delete food listings.
Student Dashboard: View and reserve available food items.
Surplus food listing display.
Reservation system with unique pickup code generation.
User profile management with picture uploads.
6.0 System Requirements6.1 Hardware
Computer or Laptop
Min 4GB RAM
Stable internet connection
6.2 Software
Laravel 10
PHP 8.0+
Composer
Node.js & NPM
MySQL
Visual Studio Code
7.0 System Design7.1 MVC Architecture
Layer	Component	Responsibility
Model	User, SurplusItem	Handles data logic, Eloquent ORM, DB interaction.
View	Blade Templates	Renders UI using Blade and Bootstrap 5.
Controller	Auth/Student/Vendor Controllers	Processes HTTP requests and business logic.
7.2 Technology Stack
Backend: Laravel 10, PHP 8+
Frontend: Bootstrap 5, Blade Engine, JavaScript
Database: MySQL
Tools: Composer, NPM
8.0 Key Features Summary
Authentication: Custom AuthController, session-based auth, and role-based redirects.
Student Module: Dynamic listings, reservation system, 6-digit pickup code generation.
Vendor Module: CRUD for food items, image upload, and listing management.
9.0 Testing Summary

Functional and UI testing were conducted across Desktop, Laptop, and Mobile resolutions.
Core Tests Passed: User Registration, Login, Reservation Flow, Quantity Management, and Profile Updates.
Responsive UI: Verified across major browsers (Chrome, Firefox, Edge).
10.0 Limitations & Future WorkLimitations
Simulation-based reservation (no real payment gateway).
No real-time WebSocket updates.
No email/push notification system.
Future Enhancements
Payment gateway integration (e.g., Stripe/FPX).
Real-time updates via WebSockets.
QR code verification.
Admin dashboard for analytics.
Mobile application development.
11.0 Conclusion

EcoBite provides a functional, scalable, and sustainable foundation for campus food waste management. By utilizing the MVC pattern and Laravel framework, we have created a robust platform that successfully addresses the core needs of both vendors and students.
