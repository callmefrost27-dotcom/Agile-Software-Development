# Project Charter: TechLeasing

---

## 1. Project Title
**TechLeasing – Short-Term Tech Hardware & Laptop Leasing Platform**

---

## 2. Project Background
In academic and professional environments, students and young professionals frequently encounter demanding computational requirements. Courses in 3D animation, game development, machine learning, video production, and software engineering require high-performance laptops equipped with modern multi-core processors, dedicated graphics processing units (GPUs), and large memory capacities.

However, purchasing high-end devices outright requires substantial capital investment—frequently exceeding 30,000 to 80,000+ THB. For many students and entry-level freelancers, these intensive hardware demands are short-lived, often tied to a two-week final project, a hackathon, an internship, or a semester module. Furthermore, tech enthusiasts often wish to evaluate a machine before committing to a costly purchase.

**TechLeasing** addresses this gap by offering a web-based rental platform that provides affordable, flexible hardware rentals on a daily, weekly, or monthly basis. By incorporating purpose-built hardware recommendations, verified student discounts, damage protection plans, and seamless pickup and delivery logistics, TechLeasing makes cutting-edge technology accessible to those who need it most without the burden of long-term debt or ownership costs.

---

## 3. Problem Statement
1. **Prohibitive Hardware Costs:** High-performance laptops (such as Apple MacBook Pros and ASUS ROG/TUF gaming workstations) carry high retail price tags that many students and entry-level professionals cannot afford.
2. **Short-Term Demand Mismatch:** Intensive compute workloads often last only a few days or weeks (e.g., a two-week Blender 3D rendering project), making outright purchase financially impractical.
3. **Fragmented & Inflexible Rental Options:** Traditional equipment rental agencies cater primarily to large corporate events, entail complex paper contracts, lack transparent student pricing, and do not offer spec-based recommendations for specific software tasks.
4. **Hardware Selection Uncertainty:** Non-technical students frequently do not know what specifications (GPU, RAM, CPU) are necessary for their coursework, leading to overspending or underpowered selections.

---

## 4. Project Purpose
The purpose of TechLeasing is to develop an accessible, transparent, and user-friendly web platform where students and professionals can discover, select, and lease high-performance laptops and electronic devices for short durations. TechLeasing aims to democratize access to cutting-edge technology through verified student discounts, purpose-oriented recommendations, and reliable equipment protection.

---

## 5. Project Objectives
1. **Build a Web-Based Rental Portal:** Deliver an intuitive, responsive web application enabling users to browse, search, configure rental periods, and reserve high-spec hardware.
2. **Implement Flexible Duration Pricing:** Support daily, weekly, and monthly leasing tiers with automatic, real-time price calculations.
3. **Offer Student Affordability:** Integrate a student identity verification workflow that awards discounted rates (e.g., 10–15% discount) to eligible university students.
4. **Develop a Purpose-Based Recommendation Tool:** Create an interactive recommendation wizard that matches user workloads (e.g., 3D Animation, Data Science, Video Editing, Software Development) and budget limits with suitable device configurations.
5. **Mitigate Financial and Equipment Risk:** Offer optional damage protection tiers and clear deposit/identification safeguards.
6. **Streamline Logistics:** Allow renters to choose between on-campus/store pickup and door-to-door courier delivery.
7. **Provide Administration Controls:** Equip platform administrators with tools to manage device inventory, inspect rental requests, update order statuses, and track device availability.

---

## 6. Project Scope

### 6.1 In Scope
- **User Account & Profile Management:**
  - User registration, login, profile management, and password security.
  - Student identity card upload and status verification.
- **Device Catalog & Exploration:**
  - Categorized browsing (e.g., 3D & Animation Laptops, Machine Learning Workstations, Ultraportables, Testing Devices).
  - Search by model name, processor, GPU, RAM, and brand.
  - Multi-attribute filtering (category, price range, RAM, GPU series, availability).
  - Detailed product pages featuring hardware specifications, rental pricing tiers, and availability indicators.
- **Smart Hardware Recommendations:**
  - Guided questionnaire matching user use-case (e.g., Blender rendering), expected duration, and budget with available laptops.
- **Booking & Rental System:**
  - Interactive date picker for rental start and return dates.
  - Dynamic cost breakdown including rental base rate, duration discounts, student discount, damage protection fee, and delivery fee.
  - Selection of delivery method (Store Pickup vs. Doorstep Delivery).
  - Optional damage protection add-on selection.
- **User Dashboard:**
  - History of past and active rental requests with current status (Pending, Confirmed, Active, Returned, Cancelled).
- **Administrative Portal:**
  - Inventory management (Create, Read, Update, Delete device records; mark devices as Available, Rented, or Maintenance).
  - Rental request management (Review requests, confirm reservations, update fulfillment status, process returns).
  - Student verification review (Approve or reject submitted student documents).

### 6.2 Out of Scope
- Direct third-party payment gateway integration with real merchant credit card processing (simulated mock payment/receipt upload will be implemented for academic project scope).
- Automated live GPS hardware tracking units installed inside devices.
- Native mobile applications for iOS and Android (the web portal will be fully responsive for mobile and tablet browsers).
- Multi-vendor marketplace capabilities (all devices in this release are owned and serviced by the TechLeasing organization).
- International shipping or cross-border rentals.

---

## 7. Target Users
1. **University Students:**
   - Undergraduates and postgraduates in computer science, digital arts, animation, architecture, and engineering who require high-performance computers for lab assignments, semester projects, or capstone presentations.
2. **Young Professionals & Freelancers:**
   - Graphic designers, video editors, and software developers who require short-term hardware for freelance contracts, travel, or client demonstrations.
3. **Tech Enthusiasts & Hardware Testers:**
   - Individuals evaluating a specific laptop model or OS platform prior to making a long-term purchase decision.
4. **Platform Administrators (TechLeasing Staff):**
   - Team members managing the device fleet, validating student documentation, scheduling deliveries, and handling equipment returns.

---

## 8. Stakeholders
- **Course Instructors & Academic Evaluators:** Oversee adherence to Agile software engineering standards and evaluate project deliverables.
- **University Student Body:** Primary consumer group benefiting from affordable short-term hardware leasing.
- **TechLeasing Management & Operations Team:** Internal operators responsible for hardware inventory, maintenance, and logistics.
- **Project Development Team:** Responsible for system design, implementation, testing, and deployment.

---

## 9. Key Features
- **User Management & Student Verification:** Secure authentication with student ID verification for discounted rates.
- **Comprehensive Hardware Catalog:** Searchable, filterable catalog of high-performance laptops and devices with detailed specs.
- **Purpose-Driven Recommendation Engine:** Interactive assistant recommending optimal devices based on user workload (e.g., Blender 3D, Premiere Pro, Deep Learning) and budget.
- **Flexible Rental Period Calculator:** Real-time pricing engine supporting daily, weekly, and monthly durations.
- **Damage Protection Coverage:** Optional add-on mitigating accidental hardware damage risks during the rental term.
- **Fulfillment Options:** Flexible selection between depot pickup and courier doorstep delivery.
- **User Order Tracking:** Dedicated portal for monitoring active reservations, return dates, and past rental history.
- **Admin Fleet & Order Dashboard:** Centralized control panel for device inventory, student verification approvals, and rental order lifecycle management.

---

## 10. Team Members and Roles

| Name | Student ID | Primary Role | Core Responsibilities |
| :--- | :--- | :--- | :--- |
| **Wathan Htat** | 6705140052 | Project Manager & Backend Architect | Project planning, backend API development, relational database architecture, business logic implementation, quality assurance. |
| **Ngyein Chan Ko** | 6705140061 | Frontend Lead & UI/UX Designer | Requirements engineering, UI/UX design and wireframing, frontend development, client-side state management, documentation lead. |

---

## 11. Major Deliverables
1. **Documentation Suite (Lab 2-3):**
   - Project Charter (`docs/project-charter.md`)
   - Requirements Specification (`docs/requirements-specification.md`)
   - Acceptance Criteria (`docs/acceptance-criteria.md`)
   - Database Design & ER Diagram (`docs/database-design.md`)
2. **Design Assets & Prototypes:**
   - UI wireframes and user journey maps for core rental workflows.
3. **Agile Project Management Artifacts:**
   - Product backlog, sprint plans, and user stories.
4. **Working Software Application:**
   - Functional frontend application (responsive catalog, recommendation wizard, booking interface).
   - Functional backend server and relational database.
5. **Testing & Demonstration:**
   - Acceptance test reports, test verification logs, and final project demonstration video/presentation.

---

## 12. Constraints
- **Academic Timeline:** The project must be completed, tested, and submitted within the assigned semester schedule following two-week Agile sprints.
- **Team Size:** The project is developed by a two-member team, requiring a disciplined scope focused on high-priority MVP features.
- **Financial Budget:** Zero external funding; development relies exclusively on open-source libraries, free-tier cloud platforms, and local development environments.
- **Payment Processing:** Due to legal and financial compliance limits for university projects, payment processing will be demonstrated via simulated checkout / transaction verification.

---

## 13. Risks and Mitigation Strategies

| Risk Description | Likelihood | Impact | Mitigation Strategy |
| :--- | :---: | :---: | :--- |
| **Hardware Damage or Loss:** Devices returned damaged, broken, or not returned by renters. | Medium | High | Require valid ID and deposit; offer optional Damage Protection plan; outline clear legal terms of service. |
| **Student Verification Abuse:** Unqualified users submitting fraudulent student IDs to claim discounts. | Low | Medium | Require manual or admin approval of uploaded student identification cards before applying student rates. |
| **Schedule Overlap / Double Booking:** Two users attempting to rent the same device for overlapping calendar dates. | Medium | High | Implement database-level reservation locking and date-range overlap validation during checkout. |
| **Scope Creep:** Over-expanding features (e.g., live GPS tracking, payment gateway compliance) beyond semester limits. | High | Medium | Strictly adhere to the MVP scope outlined in the Agile backlog; prioritize essential rental lifecycle features. |
| **Time & Coordination Bottlenecks:** Delays caused by parallel coursework and exam periods. | Medium | Medium | Maintain weekly sprint check-ins, continuous version control with Git, and modular code separation. |

---

## 14. Success Criteria
1. **Academic Rubric Compliance:** Complete and timely delivery of all project artifacts meeting Agile Software Development course requirements.
2. **End-to-End Workflow Demonstration:** A user can successfully register, submit student verification, receive a device recommendation, book a laptop with damage protection, and view the active rental in their dashboard.
3. **Operational Admin Control:** An administrator can create a new laptop listing, adjust inventory availability, approve a student discount, and advance a rental from "Requested" to "Returned".
4. **Performance & Usability:** Responsive web UI loading catalog pages within 2 seconds and completing a rental booking flow in under 3 minutes.
5. **Zero Double-Bookings:** 100% data integrity verified under concurrent date reservation tests for single inventory units.
