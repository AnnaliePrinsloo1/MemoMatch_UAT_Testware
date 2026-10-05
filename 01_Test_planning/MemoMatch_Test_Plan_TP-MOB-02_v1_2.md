# User Acceptance Test Plan: MemoMatch App (Beta)

Identifier: TP-MOB-02  
Test Level: User Acceptance Testing (UAT)  
Current Status: Completed  
Version: v1.2  
Date: 2026-09-10  
Author: Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-22 | Annalie Prinsloo | Baseline UAT Test Plan. |
| 1.2 | 2026-09-10 | Annalie Prinsloo | Fictionalized for public portfolio (app renamed to MemoMatch); identifiers migrated to the `*-MOB-02` convention; document restructured to align with the standard testware template (Test Objectives, Suspension/Resumption Criteria, Test Monitoring & Control, and Deliverables sections added); corrected the systematic "desks" → "decks" typo. |

### 1.2 References
* MemoMatch App Beta Specifications (Build V 20260518)
* ISTQB Foundation Level Syllabus (CTFL v4.0)

---

## 2. Test Objectives
MemoMatch is an ADHD-friendly educational memory-training game designed to build visual, verbal, and associative memory skills. The primary objective of this UAT phase is to ensure a stable, calm, and zero-stall user experience. Because the application targets children, teenagers, and adults with ADHD, software defects such as erratic audio, sudden animation flashes, or broken progression screens represent a high risk of sensory overstimulation and loss of user focus — so this cycle treats sensory and interruption-handling stability as first-class quality objectives alongside standard functional correctness.

---

## 3. Context & Scope
### 3.1 Context of Testing (System Under Test)
The System Under Test (SUT) is the **MemoMatch App (Beta, Build V 20260518)** for Android. This UAT phase evaluates core single-player memory-matching mechanics, sensory/accessibility customization, and interruption resilience ahead of public deployment.

### 3.2 Features to be Tested (In-Scope)
* **`REQ-MM-01` to `REQ-MM-07` (Main Menu Functions):** Background music selection (16 tracks), help modules, guided tour with narration toggle, legal document links, avatar selection, and the point redemption input field. *(Note: the redemption field's boundary validation is in scope; the underlying points/store economy is not — see Section 3.3.)*
* **`REQ-GS-01` to `REQ-GS-07` (Game Configuration Matrix):** Deck and level/pair selection (14 decks, grid ratios from 1/4 to 4/16), content/regional filters, game mode switching (Regular vs. Time Trial), card back variations, and localization (English UK vs. English US).
* **`REQ-GP-01` to `REQ-GP-09` (Core Memory Engine):** Card flip and top-navbar tracking, hint and card-info tools, match/mismatch validation, end-of-level results, ad display between levels, and quick-action progression controls.
* **`REQ-CZ-01` to `REQ-CZ-04` (Accessibility & Customization Controls):** Speech speed and master volume sliders, child/adult age-mode switching, and avatar customization.
* **`REQ-MP-01` (Premium Lockout Gate):** Verifying that Free Tier accounts are correctly blocked from multiplayer and presented with an upgrade path. *(This tests the access-control gate only — the multiplayer gameplay itself is out of scope; see Section 3.3.)*
* **`REQ-LB-01` (Leaderboard Display):** Top-3 leaderboard display with expanded view.
* **`REQ-NF-01` (Non-Functional Resilience):** App state preservation during minimization and interruption; simultaneous-input handling during active gameplay.

### 3.3 Features Not to be Tested (Out-of-Scope)
* **Daily Brain Bites, Points Redemption Engine, and Store Interfaces:** The underlying points economy and storefront transaction flows are excluded (only the redemption field's input validation is in scope, per `REQ-MM-04`).
* **Live Multiplayer Gameplay:** Live duels, active player matching, and network challenges are Premium-only features and are excluded from this testing phase. Only the Free Tier lockout gate itself (`REQ-MP-01`) is tested.
* **Non-English Localization:** Verification of the 8 non-English languages listed in the app specifications is excluded; only English UK and English US are tested.

### 3.4 Assumptions, Constraints, and Dependencies
* **Assumptions:**
  * The Google Play Beta build under test accurately reflects the intended production release candidate.
* **Constraints:**
  * Testing is restricted to a single physical device; no emulators or cloud test benches are used.
  * Testing is restricted to English UK and English US; other supported languages are not verified this cycle.
* **Dependencies:**
  * Stable Wi-Fi/cellular connectivity is required to pull the latest beta build and to verify true-online vs. false-offline banner behavior.
  * Test data lists for point values, regional filters, and decks must be loaded into the test environment before execution begins.

---

## 4. Physical Device & Environment Matrix
| Device Model | Operating System | Firmware / UI Version | Environment Type |
| :--- | :--- | :--- | :--- |
| Samsung Galaxy S21 FE 5G (Model: SM-G990E/DS, Exynos 2100) | Android 16 | Samsung One UI 8.0 | Local Physical Device |

*Note: Virtual emulators and cloud test benches are explicitly excluded from this cycle.*

---

## 5. Test Strategy & Approach
### 5.1 Test Levels and Test Types
* **Test Level:** User Acceptance Testing (UAT) / Beta Phase.
* **Test Types:**
  * **Functional Testing:** Validating card lifecycle logic, configuration matrix behavior, progression flows, and boundary input handling.
  * **Non-Functional Testing:**
    * **Usability & Accessibility Testing:** Verifying narration toggles, localization switching, slider responsiveness, and visual asset scaling.
    * **Interruption/Resilience Testing:** Simulating low-battery warnings, app minimization, device locking, and simultaneous high-frequency input during active gameplay.

### 5.2 Techniques for Test Design
* **Specification-Based Techniques:** Equivalence Partitioning (EP) and Boundary Value Analysis (BVA) applied to volume percentages (0–100%), grid sizes (1/4 to 4/16), and redemption code inputs.
* **State Transition Testing:** Validating card lifecycle states (face-down, flipped/active, matched/mismatched) and global application state transitions (level progression, ad-triggering intervals, premium content lockouts).

### 5.3 Test Automation Approach
* Completely manual execution. All test cases are executed by hand on the physical target device; no automation framework is used for this cycle.

---

## 6. Entry, Exit & Suspension Criteria
### 6.1 Entry Criteria
1. The MemoMatch test environment build is stabilized and deployed to the target device.
2. All functional requirements, tour scripts, and configuration specifications are finalized.
3. Test data lists for point values, regional filters, and decks are loaded into the test environment.

### 6.2 Exit Criteria (Acceptance Criteria)
1. 100% of all High-Priority test cases (core game logic, audio sliders, and layout switches) are executed.
2. At least 95% of total test cases pass successfully.

### 6.3 Suspension and Resumption Criteria
* **Suspension Criteria:** If the application produces rapid strobing, flashing, or other sensory effects exceeding accessibility-safe visual thresholds during testing, or if game state is irrecoverably corrupted following an interruption test.
* **Resumption Criteria:** Testing resumes once a stable build addressing the triggering issue is deployed, or once the affected sensory/state-integrity behavior is confirmed safe on retest.

### 6.4 Test Monitoring & Control
#### 6.4.1 Metrics Collected
* Test case execution progress: % of planned test cases executed to date.
* Pass/fail rate: % of executed test cases passing, tracked against the Exit Criteria threshold in Section 6.2.
* Defect metrics: open defect count by severity, logged against `BUG-MOB-02-01` onward.
* Requirements coverage: % of in-scope requirements (`REQ-MM-01` to `REQ-NF-01`) with at least one executed test condition, tracked via the RTM (`RTM-MOB-02`).

#### 6.4.2 Reporting Cadence
* Progress is reviewed against each milestone defined in Section 7.4, with a status summary recorded at the completion of each milestone.
* The Execution Log (`EL-MOB-02`) is updated on each test session, providing a continuous record between milestones.

#### 6.4.3 Control Actions
* If defect density or severity trends indicate a blocking risk to Exit Criteria (Section 6.2), remaining execution is re-prioritized toward the highest-risk requirements (see Section 8.2 Product Risks) before continuing lower-priority coverage.
* If a Suspension Criterion (Section 6.3) is triggered, testing halts and is resumed only once the corresponding Resumption Criterion is met.
* Any deviation from the schedule in Section 7.4 is documented in the Completion Report (`TSR-MOB-02`) along with the root cause.

---

## 7. Logistics, Resources & Schedule
### 7.1 Test Environment and Tools Requirements
* Target physical device (Samsung Galaxy S21 FE 5G) with stable Wi-Fi/cellular connectivity.
* Google Play Beta channel access for pulling the target build.

### 7.2 Roles, Responsibilities, and Staffing
* **UAT Project Lead & Execution Specialist:** Annalie Prinsloo
  * *Responsibilities:* Environment setup and verification, manual test execution, defect logging, and delivery of the completion report.

### 7.3 Work Breakdown and Estimates
| Task Item | Target Resource | Estimated Effort |
| :--- | :--- | :--- |
| Environment Setup & Build Verification | Annalie Prinsloo | 0.5 Hours |
| `REQ-MM-01` to `REQ-MM-07`: Main Menu & Redemption Testing | Annalie Prinsloo | 1.5 Hours |
| `REQ-GS-01` to `REQ-GS-07`: Game Configuration Matrix Testing | Annalie Prinsloo | 1.5 Hours |
| `REQ-GP-01` to `REQ-GP-09`: Core Memory Engine Testing | Annalie Prinsloo | 2.0 Hours |
| `REQ-CZ-01` to `REQ-CZ-04`, `REQ-MP-01`, `REQ-LB-01`: Customization & Lockout Testing | Annalie Prinsloo | 1.5 Hours |
| `REQ-NF-01`: Interruption & Resilience Testing | Annalie Prinsloo | 1.0 Hour |
| Defect Logging & Completion Report | Annalie Prinsloo | 1.5 Hours |

### 7.4 Milestones and Schedule
* **Milestone 1:** Build Verification & Environment Setup Sign-off — 2026-05-19
* **Milestone 2:** Full Test Case Execution Complete (21 Test Cases) — 2026-05-20
* **Milestone 3:** Defect Logging, Completion Report Issued & Signed Off — 2026-05-21

---

## 8. Communication & Risk Management
### 8.1 Communication Protocols and Status Reporting
* Testing results, defect logs, and risk observations are captured in Markdown and delivered at the close of the execution session.

### 8.2 Product Risks (Quality Risks)
| Risk ID | Risk Description | Impact Level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **PR-01** | Non-matching cards flash too brightly, or audio clips distort when the volume slider is adjusted. | High | Conduct manual visual audits against pre-approved UX contrast/brightness baselines to confirm animations do not strobe rapidly; perform physical audio sweeps across the full 0–100% volume range and varied ambient noise levels to flag clipping, crackling, or sudden volume spikes. |
| **PR-02** | The Time Trial countdown or broken state retention causes anxiety if the app is interrupted. | Medium | Verify state retention during minimization so the player never loses current level progress. |
| **PR-03** | Advertisements between levels cause app locks, or the next level fails to load fresh randomized cards. | Medium | Execute end-to-end flow testing specifically on the transitions between game grids, mini-games, and ad wrappers. |

### 8.3 Project Risks (Management Risks)
| Risk ID | Risk Description | Impact Level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **MR-01** | Single-device testing scope means device-specific rendering or performance issues on other hardware profiles go undetected this cycle. | Medium | Document this constraint explicitly (Section 3.4) and recommend multi-device coverage for a future cycle if the app targets a broader device range. |

---

## 9. Deliverables
* **Test Plan:** This document (TP-MOB-02 v1.2)
* **Requirements Traceability Matrix (RTM):** RTM-MOB-02
* **Test Conditions:** TCOND-MOB-02
* **Test Cases Suite:** TC-MOB-02
* **Test Procedures:** TPROC-MOB-02
* **Execution Log:** EL-MOB-02
* **Defect Reports:** BUG-MOB-02-01 to BUG-MOB-02-04
* **Completion Report:** TSR-MOB-02
