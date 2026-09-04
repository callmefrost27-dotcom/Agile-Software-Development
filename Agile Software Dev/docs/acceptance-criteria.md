# Acceptance Criteria Specification
## TechLeasing Platform

---

## 1. Document Overview
This document specifies the user acceptance criteria for the **TechLeasing** web platform. Each testable scenario directly maps to the Functional Requirements defined in the [Requirements Specification](file:///E:/Agile%20Software%20Dev/docs/requirements-specification.md). Scenarios are structured in standard Agile format (**User Story**, **Given**, **When**, **Then**, **Expected Result**) to guide automated testing and manual quality assurance.

---

## 2. Acceptance Criteria Scenarios

### 2.1 User Registration
- **Requirement ID:** FR-01
- **Feature:** User Registration
- **User Story:** As a new user, I want to create a TechLeasing account using my email and personal details, so that I can rent devices and track my orders.
- **Given:** The user is on the TechLeasing registration page with all required input fields empty.
- **When:** The user enters a valid full name, a unique email address, a valid phone number, a secure password (minimum 8 characters), selects account type "Student", and clicks the "Register" button.
- **Then:** The system creates a new user record with a hashed password, sets their initial role to "Customer", and displays a success notification.
- **Expected Result:** The user is redirected to the login page or automatically logged in, and an account entry is confirmed in the database.

---

### 2.2 User Login & Authentication
- **Requirement ID:** FR-02
- **Feature:** User Login & Authentication
- **User Story:** As a registered user, I want to log in using my email and password, so that I can access my profile and lease devices.
- **Given:** An existing registered user is on the login page.
- **When:** The user enters their registered email and correct password and clicks "Log In".
- **Then:** The system validates the credentials, establishes a secure user session, and updates the navigation bar to reflect an authenticated state.
- **Expected Result:** The user successfully lands on the home or catalog dashboard, and their name appears in the top navigation header.

---

### 2.3 Student Verification Submission
- **Requirement ID:** FR-03
- **Feature:** Student Verification Submission
- **User Story:** As an enrolled university student, I want to submit my student ID card image, so that I can be verified for student rental discounts.
- **Given:** A logged-in student user is on their profile or account settings page with student verification status "Not Submitted".
- **When:** The user uploads a clear image file (JPG or PNG) of their student ID card, enters their University Name and Student ID number, and clicks "Submit Verification".
- **Then:** The system uploads the document securely, creates a verification record with status "Pending", and displays a message informing the user that their submission is under review.
- **Expected Result:** The verification record appears with status "Pending", and the user interface indicates that discount benefits will activate upon admin approval.

---

### 2.4 Browse Available Devices
- **Requirement ID:** FR-04
- **Feature:** Browse Available Devices
- **User Story:** As a visitor or customer, I want to browse a catalog of high-end laptops and electronic devices, so that I can explore what hardware is available to rent.
- **Given:** The user navigates to the TechLeasing catalog page.
- **When:** The catalog page finishes loading.
- **Then:** The system displays a grid of device cards showing high-resolution product images, brand name, model name, primary specs (CPU, GPU, RAM, Storage), base daily/weekly rates, and current availability status ("Available", "Rented", or "In Maintenance").
- **Expected Result:** All active devices are visible, formatted cleanly in responsive cards, and clickable to open detailed views.

---

### 2.5 Search Devices
- **Requirement ID:** FR-05
- **Feature:** Search Devices
- **User Story:** As a user, I want to search for laptops by keywords such as model, CPU, or GPU, so that I can quickly locate specific hardware.
- **Given:** The user is on the device catalog page with multiple devices displayed.
- **When:** The user enters "Zephyrus" or "RTX 4070" into the search bar.
- **Then:** The system dynamically filters the catalog to show only device records where the title, brand, processor, or graphics card contains the search keyword.
- **Expected Result:** Only matching devices (e.g., ASUS ROG Zephyrus with RTX GPU) are displayed in the results list within 500 milliseconds.

---

### 2.6 Filter Devices
- **Requirement ID:** FR-06
- **Feature:** Filter Devices
- **User Story:** As a user, I want to filter devices by category, RAM capacity, and price range, so that I can narrow down hardware that fits my performance needs and budget.
- **Given:** The user is viewing the full catalog of devices.
- **When:** The user selects category "3D Animation & Rendering", selects RAM checkbox "32 GB", and sets a maximum daily budget of 300 THB.
- **Then:** The catalog view immediately updates to display only devices that belong to the selected category, have at least 32 GB RAM, and have a daily rental rate less than or equal to 300 THB.
- **Expected Result:** The displayed product count reflects the filtered subset, and devices not meeting all three conditions are hidden.

---

### 2.7 View Device Details
- **Requirement ID:** FR-07
- **Feature:** View Device Details
- **User Story:** As a prospective renter, I want to view the complete technical specifications and pricing tiers of a device, so that I can decide if it meets my project requirements.
- **Given:** The user is browsing the device catalog.
- **When:** The user clicks on a device card (e.g., "ASUS ROG Zephyrus G16").
- **Then:** The system navigates to the dedicated device detail page displaying detailed CPU/GPU/RAM/Storage specs, high-resolution gallery, current availability badge, and daily, weekly, and monthly pricing tables.
- **Expected Result:** All hardware attributes and rental pricing tiers are rendered clearly, and an "Initiate Rental" button is readily accessible.

---

### 2.8 Select Rental Duration & Dates
- **Requirement ID:** FR-08
- **Feature:** Select Rental Duration
- **User Story:** As a renter, I want to select my rental start date and return date on an interactive calendar, so that I can schedule my lease around my project timeline.
- **Given:** The user is on the rental configuration section of a device detail page.
- **When:** The user selects a start date of "2026-09-10" and an end date of "2026-09-24" (a 14-day rental).
- **Then:** The system validates that the start date is in the future, the end date is after the start date, the duration is at least 1 day, and no overlapping confirmed bookings exist for that specific hardware item.
- **Expected Result:** The calendar highlights the 14 selected calendar days, displays duration as "14 Days (2 Weeks)", and enables the checkout button.

---

### 2.9 Rental Price Calculation
- **Requirement ID:** FR-09
- **Feature:** Dynamic Rental Price Calculation
- **User Story:** As a renter, I want to see an itemized calculation of my rental cost based on my selected duration, so that I have transparent pricing before reserving.
- **Given:** A device has a daily rate of 300 THB and a discounted weekly rate of 1,750 THB (saving 350 THB per week).
- **When:** The user selects a 14-day duration (2 weeks).
- **Then:** The system calculates the base rental price as 2 × 1,750 = 3,500 THB, rather than 14 × 300 = 4,200 THB, and displays an itemized receipt summary.
- **Expected Result:** The pricing breakdown displays base duration rate (3,500 THB), duration discount (-700 THB savings compared to daily rate), and updates in real time as dates change.

---

### 2.10 Student Discount Application
- **Requirement ID:** FR-10
- **Feature:** Student Discount Application
- **User Story:** As a verified student, I want my student discount applied automatically to my rental order, so that I pay an affordable student rate.
- **Given:** A logged-in user whose `STUDENT_VERIFICATION` status is "Approved" proceeds to checkout for a 3,500 THB 2-week lease.
- **When:** The user views the order summary.
- **Then:** The system automatically identifies the verified student badge and applies a 10% student discount (-350 THB) against the base rental charge.
- **Expected Result:** The order summary itemizes: "Student Discount (10%): -350 THB", and the net payable balance reduces accordingly to 3,150 THB (before protection/delivery).

---

### 2.11 Device Recommendations Based on Purpose
- **Requirement ID:** FR-11
- **Feature:** Purpose-Based Device Recommendations
- **User Story:** As a university student needing hardware for a specific course assignment, I want the system to recommend the right laptop based on my software application and budget, so that I get a machine that can run my project without overpaying.
- **Given:** A student opens the "Smart Device Recommendation" wizard.
- **When:** The user selects purpose "Blender 3D Animation", specifies duration "2 weeks", and sets budget "4,000 THB".
- **Then:** The system queries available inventory for machines with dedicated RTX GPUs, at least 32 GB RAM, and a 2-week lease price under or equal to 4,000 THB.
- **Expected Result:** The wizard presents the "ASUS ROG Zephyrus" (RTX GPU, 32 GB RAM, 2-week lease: 3,500 THB) as the top recommended match, displaying a "Best Match for Blender 3D" tag with a one-click "Lease This Device" button.

---

### 2.12 Create Rental Request
- **Requirement ID:** FR-12
- **Feature:** Create Rental Request
- **User Story:** As an authenticated customer, I want to submit a complete rental order, so that my reservation is recorded and the device is held for me.
- **Given:** The user has selected a device, rental dates (e.g., 2 weeks), delivery method, and damage protection option.
- **When:** The user reviews the total cost and clicks "Confirm Rental Request".
- **Then:** The system creates a new `RENTAL` record, generates corresponding `RENTAL_ITEM`, `DELIVERY`, and `PAYMENT` records, sets rental status to "Pending", and temporarily reserves the device.
- **Expected Result:** A booking confirmation screen is displayed showing the generated Order/Rental ID, full summary, and pickup/delivery instructions.

---

### 2.13 Delivery & Pickup Selection
- **Requirement ID:** FR-13
- **Feature:** Delivery / Pickup Selection
- **User Story:** As a renter, I want to choose between picking up the laptop on campus or having it delivered to my residence, so that I can choose the most convenient option.
- **Given:** The user is on the rental checkout page configuring order fulfillment.
- **When:** The user toggles between "Store Pickup" and "Doorstep Delivery":
  - Case A: User selects "Store Pickup" and chooses "Main Campus Tech Depot".
  - Case B: User selects "Doorstep Delivery" and inputs their street address, city, postal code, and phone number.
- **Then:**
  - Case A: Delivery fee is set to 0 THB; pickup instructions and operating hours are shown.
  - Case B: A standard delivery fee (e.g., 150 THB) is appended to the order total, and address validation is enforced.
- **Expected Result:** Order total dynamically updates to reflect fulfillment choice, and the chosen option is recorded in the `DELIVERY` entity.

---

### 2.14 Damage Protection Option
- **Requirement ID:** FR-14
- **Feature:** Damage Protection Option
- **User Story:** As a student renter carrying a high-value laptop, I want to add optional damage protection, so that I am protected from expensive liability if an accidental spill or drop occurs.
- **Given:** The user is on the checkout page reviewing order add-ons.
- **When:** The user checks the "Add Damage Protection Coverage (+250 THB / week)" checkbox.
- **Then:** The system calculates the protection fee (2 weeks × 250 THB = 500 THB), updates the order total, and displays a summary of coverage terms (covering accidental drops, liquid spills, and hardware malfunctions with zero deductible).
- **Expected Result:** The itemized breakdown shows "Damage Protection: +500 THB", and the `DAMAGE_PROTECTION` record is linked to the rental.

---

### 2.15 View Rental History
- **Requirement ID:** FR-15
- **Feature:** View Rental History
- **User Story:** As a customer, I want to view my past and current rentals in my dashboard, so that I can check upcoming return dates and order statuses.
- **Given:** An authenticated user navigates to "My Rentals".
- **When:** The page loads.
- **Then:** The system retrieves and displays all rental records associated with the user's account, sorted chronologically with status badges (Pending, Confirmed, Active, Returned, Cancelled), device photos, start/end dates, and fulfillment details.
- **Expected Result:** The user can inspect full details of any previous or active rental, view receipt summaries, and see how many days remain until scheduled return.

---

### 2.16 Admin Device Management
- **Requirement ID:** FR-16
- **Feature:** Admin Device Inventory Management
- **User Story:** As a platform administrator, I want to add, edit, and update the status of devices in our fleet, so that the catalog accurately reflects our physical inventory.
- **Given:** An authenticated administrator is on the Admin Inventory Portal.
- **When:**
  - Action A: The admin enters details for a new laptop (Brand, Model, CPU, GPU, RAM, Storage, Serial Number, Daily/Weekly/Monthly Rates, Category) and clicks "Save Device".
  - Action B: The admin switches an existing device status from "Available" to "Maintenance".
- **Then:**
  - Action A: A new `DEVICE` record is inserted into the database and immediately appears in the public catalog.
  - Action B: The device status updates to "Maintenance", and it is automatically disabled from new user booking dates.
- **Expected Result:** Inventory changes persist correctly and are immediately reflected across admin and customer-facing views.

---

### 2.17 Admin Rental Management
- **Requirement ID:** FR-17
- **Feature:** Admin Rental Lifecycle Management
- **User Story:** As a platform administrator, I want to view, approve, dispatch, and mark rentals as returned, so that our team can manage physical hardware distribution.
- **Given:** An administrator is on the Admin Rental Management dashboard.
- **When:** The admin locates a rental in "Pending" status and clicks "Approve & Confirm", or locates an "Active" rental upon physical check-in and clicks "Mark as Returned".
- **Then:** The system updates the rental status accordingly ("Confirmed", "Active", or "Returned") and automatically updates the associated device's availability flag.
- **Expected Result:** Order status transitions successfully, timestamps are recorded, and the hardware device returns to "Available" status once marked returned.

---

### 2.18 Admin Student Verification Review
- **Requirement ID:** FR-18
- **Feature:** Admin Student Verification Review
- **User Story:** As an administrator, I want to review submitted student ID cards and approve or reject them, so that only genuine university students receive discounted rental rates.
- **Given:** An administrator opens the "Pending Student Verifications" list.
- **When:** The admin inspects the uploaded student card image, verifies the student name, ID number, and university name, and clicks "Approve Verification".
- **Then:** The system updates the `STUDENT_VERIFICATION` status to "Approved", logs the administrator ID and verification timestamp, and activates student discount eligibility on the user's account.
- **Expected Result:** The user receives a verified student badge on their profile, and subsequent checkouts automatically reflect the student discount.
