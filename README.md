# 📊 GreedyMeet: Optimal Meeting Slot Finder for Groups

**CSE266.9 Group Project | Fall 2025** *Optimizing collaborative scheduling through student availability analysis.*

---

## 🏛 Project Overview
**GreedyMeet** is a web-based scheduling optimization tool designed to solve the "meeting-point problem" common in academic environments. In modern university settings, coordinating group meetings amidst diverse individual course loads is a non-trivial task. 

This project utilizes a **Greedy-inspired approach** to identify the most efficient time slots for group collaboration. By collecting "busy-state" data from participants via an interactive grid, the system calculates the percentage of availability across seven days, providing visual data analytics to assist group leaders in decision-making.

---

## 👥 Research & Development Team

| Full Name | Student ID | Academic Role |
| :--- | :--- | :--- |
| **Rantu Samadder** | 2022200000149 | Lead Developer |
| **Swehinu Marma Boishakhi** | 2024000000140 | Data Analyst |

---

## 🛠 Technical Architecture

The system is architected using a decoupled **Client-Server model** to ensure scalability and lightweight performance:

### 1. Frontend Interface (The Client)
* **Engine:** HTML5, CSS3, and Vanilla JavaScript.
* **Visual Analytics:** Integrated with `Chart.js` for real-time frequency distribution mapping.
* **Styling:** A "Matrix-Cyber" aesthetic featuring dynamic binary background animations and responsive CSS Flexbox/Grid layouts.

### 2. Backend Engine (The Server)
* **Environment:** Google Apps Script (GAS).
* **Database:** Google Sheets API (acting as a persistent relational data store).
* **Logic:** Implements a custom **Overlap Detection Algorithm** that parses time-strings into integers (minutes) to calculate intersectional availability:
    $$Availability = \frac{n_{total} - n_{busy}}{n_{total}} \times 100\%$$

---

## 🚀 Core Features

* **Interactive Schedule Input:** A dynamic grid allowing students to mark "Busy" intervals.
* **Multi-Day Filtering:** Users can refine searches to specific academic days to find localized optima.
* **Data Visualization:** A bar chart dynamically renders the availability of the "Best Day" based on mean group presence.
* **Real-time Statistics:** Instant calculation of "Best Slot" (Global Maximum) and "Total Responses" count.

---

## 📖 Installation & Deployment

To deploy this project within your academic group:

1.  **Backend Setup:**
    * Create a new Google Sheet.
    * Navigate to `Extensions > Apps Script`.
    * Paste the provided `.gs` backend code.
    * Deploy as a **Web App** with "Anyone" having access.
2.  **Frontend Configuration:**
    * Open the `index.html` file.
    * Replace the `SCRIPT_URL` constant with your unique Deployment URL from step 1.
    * Launch the file in any modern web browser.

---

## 🧪 Algorithmic Methodology

GreedyMeet operates on a **Linear Time Complexity** model for data retrieval. When a group name is queried, the backend:
1.  Iterates through all recorded entries for that specific group.
2.  Maps each student to a boolean state (Busy/Free) for every 15 pre-defined meeting slots.
3.  Calculates the **Free Percentage** by subtracting the union of busy sets from the total population.

> **Note:** The "Best Slot" is defined as the interval $t$ that maximizes the function $f(t) = P(Free)$, where $P$ is the probability of member attendance.

---

## 📜 Academic Disclaimer
This project was developed for the **CSE266.9** course. It serves as a proof-of-concept for algorithmic scheduling and data synchronization.

---
**© Fall 25 GreedyMeet Development Team | All Rights Reserved.**
