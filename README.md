# IT-assests-and-Equipment-Tracker

PROJECT NAME: IT Asset & Equipment Tracker

DOMAIN:
IT / Technology

TECH STACK:
Node.js, React.js, MySQL, JWT Authentication

---

PROJECT DESCRIPTION:
The IT Asset & Equipment Tracker is a secure web application designed to manage organizational hardware and software assets. It allows authenticated users (Admins and SuperAdmins) to track assets, assign them to employees, monitor conditions, and log maintenance activities.

---

FEATURES:

* JWT-based authentication system
* Role-based access (Admin & SuperAdmin)
* Add, update, delete IT assets
* Assign/unassign assets to employees
* Track asset condition (Good, Needs Repair, Retired)
* Maintenance log management
* Filter assets by type and condition
* SuperAdmin panel to manage Admin users

---

USER ROLES:

1. SuperAdmin:

* Full access to system
* Create, update, delete Admin accounts
* Activate/Deactivate Admin users
* View all system data

2. Admin:

* Manage assets (CRUD operations)
* Assign assets to employees
* Update asset condition
* Log maintenance records

---

AUTHENTICATION:

* Users login using email and password
* JWT token is generated after login
* Token must be included in Authorization header:
  Authorization: Bearer <token>
* Token is stored in localStorage (frontend)
* Protected routes require valid token

---

API ENDPOINTS:

AUTH:
POST   /api/auth/login
GET    /api/auth/me
POST   /api/auth/logout

USER MANAGEMENT (SuperAdmin only):
GET    /api/users
POST   /api/users
PUT    /api/users/:id
PATCH  /api/users/:id/toggle
DELETE /api/users/:id

ASSET MANAGEMENT:
GET    /api/assets
GET    /api/assets/:id
POST   /api/assets
PUT    /api/assets/:id
PATCH  /api/assets/:id/condition
DELETE /api/assets/:id

FILTERING:
GET /api/assets?type=Hardware
GET /api/assets?condition=Good

---

DATABASE SCHEMA:

USER:

* id
* name
* email
* password (hashed)
* role (admin / superadmin)
* isActive
* createdAt

ASSET:

* id
* assetTag
* name
* type (Hardware/Software)
* brand
* model
* purchaseDate
* assignedTo
* condition

---

FRONTEND COMPONENTS:

* Login Page
* Dashboard (Asset Registry)
* Add/Edit Asset Form
* Asset Detail Page
* Maintenance Log Section
* Navbar (User Info + Logout)
* PrivateRoute (Protected Routes)
* SuperAdmin Panel (Admin Management)

---

HOW THE SYSTEM WORKS:

1. SuperAdmin is created directly in database
2. SuperAdmin logs in and receives JWT token
3. SuperAdmin creates Admin accounts
4. Admin logs in and manages assets
5. All API requests require token verification
6. Frontend sends token via Axios interceptor
7. Logout removes token and redirects to login

---

PROJECT STRUCTURE:

Backend:

* Models
* Controllers
* Routes
* Middleware (Auth)
* Config

Frontend:

* Pages
* Components
* Context (AuthContext)
* Services (API calls)

---

LEARNING OUTCOMES:

* JWT Authentication implementation
* Role-based access control
* CRUD operations with secure APIs
* React state management and routing
* Asset lifecycle tracking
* Backend filtering and search
* Full-stack integration

---

FUTURE ENHANCEMENTS:

* Email notifications for maintenance
* Asset depreciation tracking
* QR code integration for assets
* Export reports (PDF/Excel)
* Mobile responsive UI improvements

---

AUTHOR:
Jagadeesh

---
