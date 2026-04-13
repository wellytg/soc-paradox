# SOC Strategic Alignment Simulator: Research Test Plan

This document outlines the validation scenarios to ensure the simulator correctly captures the "Speed-Quality Paradox" for the research study.

## 🧪 Core Test Scenarios

### 1. Scenario: The "Productivity Trap" (Rapid Triage)
*   **Mode Selection:** Protocol A (Rapid Triage)
*   **User Behavior:** Focus on counting triangles quickly.
*   **Expected Result:** 
    *   **Alert Volume:** Should show as **PASSED** (High throughput).
    *   **Security Goal (Code):** Should likely be **MISSED** or **BREACHED** due to visual blur and high speed.
    *   **Analysis:** Explanation box should trigger the "Productivity Trap" message.

### 2. Scenario: The "Strategic Analyst" (Deep Review)
*   **Mode Selection:** Protocol B (Deep Review)
*   **User Behavior:** Carefully inspect each shape as it drifts slowly.
*   **Expected Result:**
    *   **Alert Volume:** Should show as **LOW** (Not meeting throughput KPI).
    *   **Security Goal (Code):** Should be **ALIGNED** (Success).
    *   **Analysis:** Explanation box should trigger the "Strategic Alignment" message.

### 3. Scenario: The "SOC Ninja" (Expert Performance)
*   **Mode Selection:** Protocol A (Rapid Triage)
*   **User Behavior:** Exceptional focus; correctly identifies the digit inside the blurred triangles while maintaining count.
*   **Expected Result:**
    *   **Triangle Count:** Correct (±1 margin).
    *   **Threat Code:** Correct.
    *   **Security Goal:** **ALIGNED** (Success).
    *   **Analysis:** Explanation box should trigger the special **"SOC NINJA DETECTED!"** message (Rare case <5%).

### 4. Scenario: The "Failed Precision" (Slow & Distracted)
*   **Mode Selection:** Protocol B (Deep Review)
*   **User Behavior:** Selects slow mode but fails to identify the code or count correctly.
*   **Expected Result:**
    *   **Alert Volume:** **LOW**.
    *   **Security Goal:** **BREACHED**.
    *   **Analysis:** Shows that even with more time, the security objective was not met.

---

## 📊 Data Integrity & Sync Verification
| Test Action | Expected Database Outcome |
| :--- | :--- |
| **Complete Game (Anonymous)** | A new document appears in `artifacts/soc-paradox-sim/public/data/leaderboard`. |
| **Refresh Page** | The "Analyst #" in the top right increments (e.g., #001 -> #002). |
| **View Leaderboard** | The new entry appears at the top of the table within ~2 seconds of submission. |
| **Tamper Test** | Attempting to delete a row from the browser console should fail (blocked by Firestore Rules). |

## 🛠️ Technical Edge Cases
- **Zero Input:** Submitting a report with empty fields should record as 0/Incorrect (No crash).
- **Mobile/Small Screen:** Ensure the "Alert Stream" container doesn't overflow or break the layout.
- **Network Lag:** Ensure the "Begin New Shift" button remains disabled until Firebase Auth is confirmed.
