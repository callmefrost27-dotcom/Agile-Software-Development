# Software Requirements Specification (SRS)
## TechLeasing Platform

---

## 1. Introduction

### 1.1 Document Overview
This Software Requirements Specification (SRS) document details the functional and non-functional requirements for **TechLeasing**, a web-based rental and leasing platform designed for high-end laptops and electronic hardware. It serves as the primary agreement between stakeholders, developers, and testers for the Agile development lifecycle.

### 1.2 System Overview
TechLeasing allows university students, freelancers, and tech enthusiasts to rent high-performance computers (e.g., GPU-powered workstations, Apple Silicon MacBooks) for short-term periods (daily, weekly, or monthly) at affordable rates. The platform features an intelligent recommendation assistant based on software workload, integrated student discounts, damage protection coverage, flexible fulfillment choices, and comprehensive administrator fleet management.

---

## 2. Purpose
The purpose of this specification is to:
- Define all functional capabilities required to implement the TechLeasing web platform.
- Establish measurable non-functional criteria for performance, security, usability, and reliability.
- Provide a clear baseline for creating user stories, sprint backlogs, acceptance criteria, and system test suites.

---

## 3. Target Users

| User Role | Description | Key Objectives |
| :--- | :--- | :--- |
| **Guest Visitor** | An unauthenticated public user exploring the platform. | Browse device catalog, search hardware, test recommendation wizard, and register for an account. |
| **Registered Customer** | A standard authenticated user (e.g., freelancer, professional, or tech tester). | Rent devices, select damage protection and fulfillment, calculate pricing, and track order history. |
| **Verified Student Customer** | A university student who has submitted a verified student ID card. | Access student-exclusive rental discounts (e.g., 10–15% off) and personalized academic device recommendations. |
| **System Administrator** | TechLeasing staff and operations personnel. | Manage device listings and inventory status, review and approve student verifications, and supervise rental order lifecycles. |

---

## 4. User Requirements

- **UR-01 (Access & Profile):** As a user, I want to create an account and manage my personal profile and university affiliation easily.
- **UR-02 (Discovery):** As a user, I want to browse, search, and filter laptops by technical specifications (e.g., GPU, RAM, OS) so that I find the right device for my specific task.
- **UR-03 (Recommendation):** As a student unfamiliar with complex hardware specs, I want the system to recommend a laptop based on the software I plan to use (e.g., Blender, Premiere, AutoCAD) and my available budget.
- **UR-04 (Flexible Leasing):** As a renter, I want to pick custom start and end dates with clear daily, weekly, or monthly pricing and see all fees upfront.
- **UR-05 (Protection & Convenience):** As a renter, I want the choice to add accidental damage protection and select between campus pickup and doorstep delivery.
- **UR-06 (Tracking):** As a customer, I want to view my past and current rental statuses and due dates in a centralized dashboard.
- **UR-07 (Administration):** As an admin, I want to manage device inventory, approve student verification proofs, and update order fulfillment statuses.

---

## 5. Functional Requirements

### 5.1 Authentication and Account Management
- **FR-01: User Registration**
  - The system shall allow new users to register with their full name, email address, phone number, password, and account type (Student or General User).
  - The system shall validate that the email address is unique and properly formatted.
  - The system shall securely hash passwords before storing them.

- **FR-02: User Authentication & Session Management**
  - The system shall authenticate users using their registered email address and password.
  - The system shall support secure session management (e.g., JWT or session cookies) and provide a logout capability.
  - The system shall distinguish between standard customer roles and administrator roles.

- **FR-03: Student Verification Submission**
  - The system shall allow registered student users to upload proof of academic enrollment (e.g., Student ID card image or university enrollment document).
  - The system shall store verification requests in a "Pending" state until reviewed by an administrator.

### 5.2 Device Exploration & Discovery
- **FR-04: Browse Available Devices**
  - The system shall display a catalog of all active electronic devices with images, brand, model name, primary specs (CPU, GPU, RAM, Storage), and base rental rates.
  - The system shall visually indicate whether a device is "Available", "Rented", or "In Maintenance".

- **FR-05: Search Devices**
  - The system shall provide a search bar that queries devices in real time by brand name, model name, processor type, and GPU model.

- **FR-06: Filter Devices**
  - The system shall enable users to filter the device catalog by category (e.g., 3D Animation & Rendering, Data Science & AI, Ultralight Business, Video Editing).
  - The system shall enable filtering by hardware attributes: RAM capacity (e.g., 16GB, 32GB, 64GB), GPU tier, Operating System (Windows, macOS, Linux), and price range.

- **FR-07: View Device Details**
  - The system shall provide a dedicated detail page for each device displaying full technical specifications, high-resolution product photos, included accessories, usage guidelines, and daily/weekly/monthly rental price tiers.

### 5.3 Rental Configuration & Pricing Engine
- **FR-08: Select Rental Duration**
  - The system shall provide an interactive calendar date-picker allowing users to specify rental start and end dates.
  - The system shall enforce a minimum rental duration of 1 day and calculate total elapsed rental days.
  - The system shall ensure the selected dates do not conflict with existing confirmed bookings for that specific device unit.

- **FR-09: Rental Price Calculation**
  - The system shall dynamically compute the total rental cost based on duration tiers:
    - Daily rate applied for 1–6 days.
    - Discounted weekly rate applied for 7–29 days.
    - Discounted monthly rate applied for 30+ days.
  - The system shall display an itemized cost summary showing base rental cost, damage protection fee, delivery fee, student discount, and total payable amount.

- **FR-10: Student Discount Application**
  - The system shall automatically apply a verified student discount (e.g., 10% off base rental cost) if the authenticated user has an approved `STUDENT_VERIFICATION` status.
  - The system shall show the discount breakdown clearly on the checkout summary.

- **FR-11: Device Recommendations Based on Purpose**
  - The system shall provide an interactive recommendation tool that asks users:
    1. Primary intended use / software application (e.g., 3D Animation with Blender, 4K Video Editing with Premiere Pro, Machine Learning with PyTorch, Everyday Academic Work).
    2. Rental duration (days/weeks).
    3. Target budget (THB).
  - The system shall filter and rank matching devices meeting the minimum required hardware profile (e.g., RTX GPU and ≥32GB RAM for Blender 3D animation) within the user's budget.

### 5.4 Booking, Fulfillment, and Protection
- **FR-12: Create Rental Request**
  - The system shall allow an authenticated user to submit a rental reservation containing the selected device, rental dates, chosen fulfillment method, and protection package.
  - The system shall assign a unique Rental ID and set the initial status to "Pending".

- **FR-13: Delivery and Pickup Selection**
  - The system shall allow users to choose between two fulfillment methods:
    1. **Self Pickup:** User selects a designated TechLeasing campus pickup depot at no additional charge.
    2. **Doorstep Delivery:** User enters a shipping address, recipient contact, and preferred delivery notes; a standard delivery fee is added to the order.

- **FR-14: Damage Protection Option**
  - The system shall allow users to opt into a Damage Protection plan during checkout.
  - The system shall clearly display coverage terms (covering accidental spills, screen drops, and minor hardware defects) and add the protection fee to the total calculation.

- **FR-15: View Rental History**
  - The system shall provide a "My Rentals" portal where users can review all past and active rental requests.
  - The system shall display order details: Rental ID, device name, start/end dates, fulfillment mode, payment status, and order status (Pending, Confirmed, Active, Returned, Cancelled).

### 5.5 Administration & Inventory Operations
- **FR-16: Admin Device Management**
  - The system shall allow authorized administrators to add new devices, update existing specifications and rental rates, upload device imagery, and archive inactive items.
  - The system shall allow administrators to change device availability status (Available, Rented, Maintenance).

- **FR-17: Admin Rental Management**
  - The system shall allow administrators to view all submitted rental orders.
  - The system shall allow administrators to approve or decline rental requests, confirm device dispatch/pickup, mark devices as returned, and update payment statuses.

- **FR-18: Admin Student Verification Review**
  - The system shall allow administrators to view pending student verification submissions, inspect uploaded credentials, and mark the status as "Approved" or "Rejected".

---

## 6. Non-Functional Requirements

### 6.1 Usability (NFR-01)
- **NFR-01.1:** The user interface shall follow clean visual hierarchy and intuitive navigation suitable for university students and general users.
- **NFR-01.2:** A user shall be able to find a suitable device and complete a rental request in under 5 minutes without prior training.
- **NFR-01.3:** Form validation errors shall be presented with clear, actionable inline feedback.

### 6.2 Performance (NFR-02)
- **NFR-02.1:** Web pages shall render the initial visible viewport within 2.0 seconds under standard broadband/4G connections.
- **NFR-02.2:** Real-time catalog search and multi-attribute filter results shall update in under 500 milliseconds.
- **NFR-02.3:** Price calculation updates triggered by date-picker changes shall execute client-side instantly (< 100ms).

### 6.3 Security (NFR-03)
- **NFR-03.1:** User passwords shall be salted and hashed using industry-standard algorithms (e.g., bcrypt) prior to database persistence.
- **NFR-03.2:** Sensitive API endpoints (admin operations, rental creation, profile changes) shall be protected using authenticated session tokens (JWT or HTTP-only cookies).
- **NFR-03.3:** All input fields shall be sanitized against Cross-Site Scripting (XSS) and SQL Injection vulnerabilities.
- **NFR-03.4:** Student identification documents shall be stored in access-restricted storage accessible only to administrators.

### 6.4 Reliability & Data Integrity (NFR-04)
- **NFR-04.1:** The system shall prevent double-booking of any individual hardware unit for overlapping date ranges through atomic database transactions.
- **NFR-04.2:** System state transitions for rentals (e.g., Pending -> Confirmed -> Active -> Returned) shall be logged with timestamps to ensure traceability.

### 6.5 Responsive Design (NFR-05)
- **NFR-05.1:** The web platform shall be fully responsive across mobile (min 375px), tablet (min 768px), and desktop (min 1280px) viewports.
- **NFR-05.2:** Navigation menus, product cards, filter bars, and modal dialogues shall resize smoothly across all standard browsers (Chrome, Firefox, Safari, Edge).

### 6.6 Maintainability (NFR-06)
- **NFR-06.1:** Source code shall follow modular software architecture principles with clear separation between presentation, business logic, and data access layers.
- **NFR-06.2:** The relational schema shall adhere to Third Normal Form (3NF) to eliminate data redundancy and anomalies.
- **NFR-06.3:** Code shall follow consistent linting rules and include descriptive comments for complex business calculations.

---

## 7. System Requirements

### 7.1 Client-Side Requirements
- **Hardware:** Any modern device (PC, Mac, laptop, tablet, or smartphone) capable of running a modern web browser.
- **Software:** Modern evergreen web browser supporting ECMAScript 6+ and HTML5 (Google Chrome 110+, Mozilla Firefox 110+, Apple Safari 16+, Microsoft Edge 110+).
- **Network:** Active internet connection with minimum 1 Mbps bandwidth.

### 7.2 Server-Side Requirements (Target Architecture)
- **Runtime Environment:** Node.js (v18+ LTS) or Python (3.10+).
- **Web Application Framework:** Express.js / Fastify (Node.js) or Flask / FastAPI (Python).
- **Database Management System (DBMS):** Relational SQL Database (PostgreSQL 14+ or MySQL 8.0+ / SQLite 3 for local development).
- **Storage:** Local or cloud object storage for device images and student verification documents.

---

## 8. Assumptions and Constraints

### 8.1 Assumptions
1. All users interacting with the platform have basic digital literacy and access to an active email account.
2. The physical inventory of devices is maintained, inspected, and serviced by TechLeasing operational staff.
3. Student verification is required only once per academic year to qualify for student rental rates.
4. Rental periods are measured in whole calendar days (from 10:00 AM start date to 6:00 PM return date).

### 8.2 Constraints
1. **Academic Project Constraints:** Developed as a university Agile Software Development laboratory project within a semester timeline.
2. **Team Resource Constraints:** Built and maintained by a 2-person student development team.
3. **Financial Constraints:** Zero budget allocation for proprietary APIs, commercial hosting, or paid payment gateways; all libraries and tools must be open source or free tier.
4. **Mocked Payment Gateway:** Actual live financial card transactions are out of scope; a mock payment confirmation workflow will be utilized.
