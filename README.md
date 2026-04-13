# SOC Strategic Alignment Simulator (soc-paradox-sim)

A research-oriented single-file web application designed to simulate the "Speed-Quality Paradox" in Security Operations Centers (SOC).

## 🎯 Project Objective
This simulator explores the trade-offs between:
- **Manager KPI (Alert Volume):** Focuses on throughput and closing tickets quickly.
- **CISO Goal (Detection Quality):** Focuses on precision and identifying hidden Indicators of Compromise (IoC).

## 🛠️ Technical Stack
- **Frontend:** HTML5, Tailwind CSS (via CDN).
- **Backend:** Firebase (Authentication & Firestore) for real-time global leaderboard sync.
- **State Management:** Vanilla JavaScript.

## 🚀 Features
- **Protocol A (Rapid Triage):** High volume, saturated alert stream with visual blur to simulate cognitive load.
- **Protocol B (Deep Review):** Low volume, clear stream for semantic review and precision.
- **Real-time Leaderboard:** Synchronizes results across all participants using Firestore.
- **Strategy Coherence Audit:** Provides an automated analysis of the user's performance relative to the chosen strategy.

## ⚙️ Configuration
The application requires a Firebase configuration. Replace the following placeholders in `index.html`:
- `__firebase_config`: Your Firebase project configuration JSON.
- `__app_id`: (Optional) Custom application identifier.

## 📄 License
Research Project - Internal Use Only.
