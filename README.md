# 🏋️ TrainerX: Mobile Fitness Ecosystem (Taiwan MVP)

TrainerX is a fitness management platform built for the Taiwan market, designed to bridge the gap between personal trainers and their students. I led the mobile architecture, task pipeline management, and delivery of the production-ready MVP.

---

### 🛠️ The Tech Stack

| Component | Technology |
| :--- | :--- |
| **Frontend** | <img src="https://skillicons.dev/icons?i=react,ts" width="35" /> **React Native (Expo)** |
| **Backend/Web** | <img src="https://skillicons.dev/icons?i=nextjs,supabase" width="35" /> **Next.js & Supabase** |
| **Analytics** | <img src="https://skillicons.dev/icons?i=googleanalytics" width="35" /> **Google Analytics** |
| **Tools** | <img src="https://skillicons.dev/icons?i=git,github,notion" width="35" /> **Notion / Git** |

---

## 🏗️ Engineering Deep-Dive

### 1. High-Reliability Calendar Sync Engine
I engineered a multi-layered synchronization system to manage trainer schedules with 100% data integrity.

* **Conflict Prevention:** The system fetches all Google Calendar events within a **6-month window**. Before a trainer creates a new class, the app cross-references the request against these existing events. If a conflict is detected, the system blocks the creation and alerts the trainer to the specific overlapping event.
* **Dual-Layer Sync:**
    * **Real-time:** Implemented Google "Automatic Events" to trigger an immediate sync the moment a trainer creates a calendar entry.
    * **The Fallback (Cron Jobs):** To handle potential webhook failures, I built a secondary **Cron Job** architecture that runs nightly to reconcile missed events, ensuring the local database stays in perfect harmony with Google.

### 2. Intelligent Localization (i18n)
To ensure a native experience for the Taiwan market, I implemented an auto-detecting localization engine.
* **Logic:** Upon app launch, the system performs a runtime check of the device's system language.
* **Behavior:** If the device is set to **Traditional Chinese**, the app automatically applies the Chinese locale. Otherwise, it gracefully defaults to **English**.
* **Scalability:** By decoupling language strings from the UI components, I ensured the codebase remains clean and easy to maintain as the product expands.

### 3. Ecosystem Integration (LINE API)
* **Challenge:** Seamlessly transitioning users from chat notifications into the app.
* **Solution:** I engineered a deep-linking bridge using the **LINE Messaging API**. Students receive class reminders in LINE and are directed straight to the specific "Course Detail" screen in the app, significantly improving user engagement.

### 4. AI-Accelerated Workflow
To meet the aggressive MVP deadline, I leveraged **Cursor and Claude AI** to rapidly prototype the supporting Next.js web dashboard while I architected the core React Native logic. This AI-assisted workflow reduced the development cycle by approximately 40% while maintaining modular, maintainable code.

---

## 📐 Best Practices & Ownership
* **State Management:** Implemented **Redux** for centralized, predictable state management across the scheduling and user-profile modules.
* **Documentation:** I maintain a living library of reusable UI components in **Notion**, ensuring the client’s team can maintain the project with zero friction.
* **Ownership:** I managed the full project lifecycle, translating high-level business requirements into technical specs and store-ready deployments.

---

## 🚀 Impact & Results
* **Data Integrity:** The dual-layer sync (Webhook + Cron) effectively eliminated the scheduling conflicts that plagued the client’s previous system.
* **User Retention:** The LINE-to-App deep-linking strategy became the primary driver for turning passive notifications into active app sessions.

---

### 📥 Technical Discussion
I am passionate about building robust, hardware-interfacing, and highly localized mobile systems. If you'd like to discuss the architecture of this project, my approach to localization, or complex API integrations, let's connect.

[LinkedIn](https://linkedin.com/in/shah-khalid-react-native) • [GitHub Profile](https://github.com/ShahKhalid808)
