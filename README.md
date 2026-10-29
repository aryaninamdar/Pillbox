
# 💊 PillBox — Smart Medication Management

PillBox is a full-stack iOS and watchOS application designed to address everyday challenges in medication management. Specificially, the app simplifies prescription tracking, improves medication adherence, and streamlines communication with healthcare providers. Built with **SwiftUI, Python, Flask, and Firebase Firestore**, PillBox offers an intuitive platform for patients to organize their prescriptions, manage daily dosing schedules, track medication completion, and request refills.

## ✨ Features

### 💊 Medication Management
- Add and organize prescriptions with customizable medication names, dosages, and administration instructions.
- Configure multiple daily dosing times for individual medications.
- View all registered prescriptions in a centralized medication inventory.
- Automatically incorporate newly added medications into the daily schedule.

### 📅 Daily Scheduling & Adherence Tracking
- View a personalized dashboard displaying scheduled medications in chronological order.
- Access medication details, including scheduled times, dosages, and instructions.
- Mark medications as taken, dynamically updating the remaining daily schedule.
- Maintain persistent medication schedules with backend functionality to restore daily dosing routines.
- Receive interactive visual feedback when completing scheduled doses.

### 🏥 Prescription Refills & Provider Information
- Submit prescription refill requests directly from the medication management interface.
- Store and track refill requests through healthcare provider records.
- View healthcare provider information and medications ready for pharmacy pickup.
- Access pharmacy pickup locations and prescription details in a dedicated provider dashboard.

### ☁️ Cloud-Backed Data Management
- Persist patient profiles, medication records, dosing schedules, and provider information using Firebase Firestore.
- Synchronize application data with a Python Flask backend through RESTful API requests.
- Dynamically refresh medication information following updates and completed doses.
- Manage application state using SwiftUI and Combine for a responsive user experience.

## 🛠️ Tech Stack

| Component | Technologies |
|-----------|-------------|
| **iOS Frontend** | Swift, SwiftUI, Combine |
| **Backend** | Python, Flask |
| **Database** | Firebase Firestore |
| **API Communication** | REST APIs, URLSession, JSON |
| **Development Tools** | Xcode, Git, GitHub |
| **Additional** | Firebase Admin SDK, ConfettiSwiftUI |

## 🏗️ System Architecture

PillBox follows a three-tier client-server architecture that separates the user interface, application logic, and data persistence.

**1. iOS Application (SwiftUI)**
- Provides interactive screens for medication management, daily scheduling, and provider information.
- Uses observable state management to dynamically update the interface.
- Communicates with the backend through asynchronous HTTP requests using URLSession.

**2. Backend REST API (Python/Flask)**
- Exposes endpoints for retrieving patient data, adding medications, tracking completed doses, resetting schedules, and requesting prescription refills.
- Implements medication scheduling logic and processes database operations.
- Serves as the intermediary between the iOS application and Firebase Firestore.

**3. Cloud Database (Firebase Firestore)**
- Stores medication details, recurring schedules, daily dosing records, and provider information.
- Maintains persistent patient data across application sessions.
- Supports structured document updates for medication and prescription workflows.

The repository also includes a foundational **watchOS application project** for future Apple Watch functionality.

## 🔌 REST API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Backend health-check response |
| `POST` | `/get-data` | Retrieve patient medication and provider data |
| `POST` | `/add-medication` | Register a medication and update its dosing schedule |
| `POST` | `/take-med` | Record a completed dose by updating the daily schedule |
| `POST` | `/reset-schedule` | Restore the daily schedule from recurring prescriptions |
| `POST` | `/request-refill` | Submit and store a prescription refill request |

## 📁 Project Structure

```text
Pillbox/
├── Backend/
│   ├── app.py                  # Flask REST API
│   ├── firebase.py             # Firestore operations and scheduling logic
│   └── requirements.txt        # Python dependencies
│
├── PillBoxIOS/
│   ├── Pillbox/                # SwiftUI iOS application
│   │   ├── HomeView.swift
│   │   ├── MedicationsView.swift
│   │   ├── AddMedicationView.swift
│   │   ├── ProviderView.swift
│   │   ├── HistoryView.swift
│   │   ├── Functions/          # Backend API communication
│   │   └── Storage/            # Application state management
│   └── Pillbox.xcodeproj
│
├── WatchOS/                    # watchOS companion app scaffold
└── README.md
```

## 🚀 Future Enhancements

- **Smart Reminders:** Push notifications and customizable alerts for upcoming medication doses.
- **Adherence Analytics:** Historical dose tracking, adherence statistics, and medication completion trends.
- **Apple Watch Integration:** Medication reminders, dose completion, and synchronization through a watchOS companion application.
- **Secure Authentication:** Individual user accounts with authenticated access to personal medication records.
- **Healthcare Connectivity:** Expanded integrations with pharmacies and healthcare providers for prescription management.


Developed as a healthcare-focused software engineering project, PillBox demonstrates the integration of native iOS development, RESTful backend services, cloud database management, and interactive medication scheduling into a unified application.
