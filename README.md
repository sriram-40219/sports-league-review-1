# Sports League Management System (SLMS)
## Skill Development Course (SDC) • Problem Statement #50 • Review 1 Submission

[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![CSS Grid & Flexbox](https://img.shields.io/badge/CSS-Grid%20%26%20Flexbox-264DE4?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
[![LocalStorage](https://img.shields.io/badge/Storage-LocalStorage-10B981)](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
[![Milestone](https://img.shields.io/badge/Milestone-Review%201%20Phase%201-blue)](https://github.com)

---

## 📌 Project Overview (Review 1 Milestone)
The **Sports League Management System (SLMS)** is an end-to-end web platform designed to streamline tournament administration, team roster registration, fixture scheduling, real-time match tracking, and fan ticketing.

This repository represents the **Review 1 (Phase 1 Prototype)** milestone focusing on:
1. **Core Problem Statement (#50)** and system requirements analysis.
2. **Decoupled System Architecture**: Clear module separation between the **Admin Console** and the **Fan / User Portal**.
3. **Pure CSS Grid & Flexbox Layouts**: Multi-dimensional card grids and single-dimensional responsive navigation bars without external UI component libraries.
4. **Persistent LocalStorage Authentication**: User registration, role evaluation (`admin` vs. `user`), and automated **module-wise redirection** with client-side route guards.
5. **Initial Domain Data Schemas**: Structured entity models for Users, Leagues, Teams, Fixtures, and Stadium Seating.

---

## 🏛️ System Architecture (Review 1)

```
                       +-----------------------------+
                       |        App.jsx (Root)       |
                       |      <AppProvider />        |
                       +--------------+--------------+
                                      |
         +----------------------------+----------------------------+
         |                                                         |
+--------v--------+                                       +--------v--------+
|   Navbar.jsx    |                                       |   Footer.jsx    |
| (Brand, Module  |                                       |  (System Stats  |
|  Switcher, Auth)|                                       |  & SDC Credit)  |
+--------+--------+                                       +-----------------+
         |
         +------------------------------------+
         |                                    |
+--------v----------------------+    +--------v----------------------+
|       User / Fan Module       |    |         Admin Module          |
|  (UserDashboard, Wireframes)  |    |  (AdminDashboard, Wireframes) |
+-------------------------------+    +-------------------------------+
         |                                    |
         +-----------------+------------------+
                           |
            +--------------v--------------+
            |      AppContext.jsx         |
            | - loadStorage / saveStorage |
            | - login() / signup()        |
            | - navigateModule() Guard    |
            | - Initial Seed Schemas      |
            +--------------+--------------+
                           |
            +--------------v--------------+
            |    Browser LocalStorage     |
            |  `slms_users`, `slms_leagues`|
            +-----------------------------+
```

---

## 🔑 Phase 1 Deliverables Implemented

### 1. Module-Wise Redirection & Role Guards (Requirement #6)
- Evaluates user role directly from LocalStorage session on login.
- Admins are automatically routed to the **Admin Module** (`currentModule = 'admin'`).
- Regular fans are automatically routed to the **User Module** (`currentModule = 'user'`).
- Route guard intercepts unauthorized attempts to view administrative pages and displays an alert.

### 2. Pure CSS Grid & Flexbox Implementation (Requirement #4)
- **CSS Grid**: Dashboard KPI cards (`.grid-cols-4`, `.grid-cols-3`), multi-column league overviews.
- **Flexbox**: Dynamic top navigation bar (`.navbar`), module switcher pills (`.module-switcher`), and sub-navigation tabs (`.subnav-tabs`).

### 3. Client-Side Authentication (Requirement #5)
- LocalStorage key: `slms_users` (credentials and role storage) and `slms_current_user` (session token).
- Includes **1-Click Demo Logins** for immediate evaluator testing:
  - **Admin Demo**: `admin@sportshub.com` / `admin123`
  - **Fan Demo**: `alex@fan.com` / `fan123`

---

## 👥 3-Person Team Roles (Review 1 Defence)

| Team Member | Role | Review 1 Defense Responsibilities |
| :--- | :--- | :--- |
| **Presenter 1** | **System Architect & Auth Lead** | Problem statement, module decomposition, React Context tree, and LocalStorage authentication mechanism. |
| **Presenter 2** | **Admin Operations Specialist** | Admin module wireframes, schema design for leagues, teams, and fixture allocation. |
| **Presenter 3** | **Fan UI & Algorithms Lead** | Fan portal wireframes, CSS Grid KPI cards, responsive layout verification, and LocalStorage inspector. |

---

## 🚀 Running the Review 1 Project Locally

```bash
# 1. Clone the repository
git clone https://github.com/sriram-40219/sports-league-review-1.git

# 2. Navigate to project directory
cd sports-league-review-1

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
```

The application will launch on `http://localhost:3000` (or the port specified by Vite).

---

## 🔮 Phase 2 Roadmap (For Review 2)
The following operational engines are scheduled for **Review 2 (Phase 2 Full Implementation)**:
- [x] Review 1 Complete: Architecture, Layouts, Auth, and Schemas
- [ ] Review 2: Multi-sport League, Team & Player Roster CRUD Operations
- [ ] Review 2: Real-time Live Match Controller (+1/-1 scoring and event broadcaster)
- [ ] Review 2: Dynamic Standings Calculation Algorithm (points and goal difference sorting)
- [ ] Review 2: 8-Column CSS Grid Interactive Stadium Seat Map & Scannable QR Code Passes
