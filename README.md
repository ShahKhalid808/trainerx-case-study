# 🏋️ TrainerX: Fitness Management Ecosystem (Taiwan MVP)

TrainerX is a fitness management platform built for the Taiwan market, designed to bridge the gap between personal trainers and their students. I led the end-to-end architecture, delivering both a **React Native mobile app for Trainers** and a **Next.js web interface for Students** (integrated directly into LINE via WebView).

---

### 🛠️ The Tech Stack

| Component | Technology |
| :--- | :--- |
| **Trainer App** | <img src="https://skillicons.dev/icons?i=react,ts" width="35" /> **React Native (Expo)** |
| **Student Web/LINE** | <img src="https://skillicons.dev/icons?i=nextjs,supabase" width="35" /> **Next.js & Supabase** |
| **Backend/Auth** | <img src="https://skillicons.dev/icons?i=supabase" width="35" /> **Supabase (Auth & Database)** |
| **Analytics** | <img src="https://skillicons.dev/icons?i=googleanalytics" width="35" /> **Google Analytics** |

---

## 🏗️ Engineering Deep-Dive

### 1. Unified Fitness Ecosystem
* **Trainer Side (Mobile):** I architected a React Native application that allows trainers to manage schedules, bookings, and student data on the go.
* **Student Side (LINE/Web):** To maximize accessibility in the Taiwan market, I built a Next.js web application optimized for the **LINE WebView**. This allows students to book sessions directly from their chat window, without ever needing to download an app.

### 2. High-Reliability Calendar Sync Engine
I engineered a multi-layered synchronization system to manage trainer schedules with 100% data integrity.
* **Conflict Prevention:** The system fetches all Google Calendar events within a **6-month window**. Before a trainer creates a new class, the system cross-references the request against these events.
* **Sync Strategy:** I implemented Google "Automatic Events" (Webhooks) for real-time updates. To handle potential webhook failures, I built a **nightly Cron Job** that reconciles the Supabase database with Google, ensuring the trainer's availability is always accurate for the students' booking interface.

### 3. Intelligent Localization (i18n)
To ensure the platform felt native for the Taiwan market:
* **Auto-detection:** Both the Mobile and Web apps perform a runtime check of the system language.
* **Dynamic Content:** If the device/browser language is set to **Traditional Chinese**, the UI automatically applies the Chinese locale; otherwise, it gracefully defaults to **English**.

### 4. Ecosystem Integration (LINE API)
* **The Bridge:** I engineered a deep-linking bridge using the **LINE Messaging API**. 
* **User Flow:** When a student books a session, they receive an automated LINE notification. Clicking this link opens the Next.js web interface inside the LINE browser, where they can confirm their booking instantly.

---

## 📐 Best Practices & Ownership
* **Data Flow:** Used **Redux** (Mobile) and **Supabase hooks** (Web) to ensure real-time data consistency between the trainer's dashboard and the student's booking view.
* **Documentation:** I maintained a living library of reusable UI components in **Notion**, ensuring the client’s team could handle future maintenance with zero friction.
* **AI-Accelerated Workflow:** I utilized **Cursor and Claude AI** to rapidly prototype the Next.js web interface while I architected the core mobile logic, reducing delivery time by 40%.

---

## 🚀 Impact & Results
* **Unified Experience:** Successfully bridged the gap between professional-grade trainer tools and a simplified, accessible student booking experience.
* **Data Integrity:** The dual-layer sync (Webhook + Cron) effectively eliminated the scheduling conflicts that previously plagued the client.
* **Scalable Launch:** The combination of a native mobile app and a lightweight LINE-integrated web app significantly boosted student conversion rates.

---

### 📥 Technical Discussion
I am passionate about building robust, multi-platform ecosystems. If you'd like to discuss the integration between React Native and Next.js, or how I handle secure Supabase auth across platforms, let's connect.

[LinkedIn](https://linkedin.com/in/shah-khalid-react-native) • [GitHub Profile](https://github.com/ShahKhalid808)
