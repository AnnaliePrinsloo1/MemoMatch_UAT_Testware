<div align="center">

### Tech Stack
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Testing Scope
![UAT](https://img.shields.io/badge/UAT-000080?style=for-the-badge&logo)
![Functional](https://img.shields.io/badge/Functional-000080?style=for-the-badge&logo)
![Non--Functional](https://img.shields.io/badge/Non--Functional-000080?style=for-the-badge&logo)
![Usability](https://img.shields.io/badge/Usability-000080?style=for-the-badge&logo)

### Test Environment
![Samsung](https://img.shields.io/badge/Samsung-%231428A0.svg?style=for-the-badge&logo=samsung&logoColor=white&logoSize=auto)
![Android](https://custom-icon-badges.demolab.com/badge/Android%2016-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Documentation reviewed with
![Claude](https://img.shields.io/badge/claude-%23D97757.svg?style=for-the-badge&logo=claude&logoColor=white)

</div>

# MemoMatch App (Beta) - End-to-End User Acceptance Test (UAT) Run

*Note on confidentiality: The app name and branding used in this repository have been fictionalized. Manual testing engagements are confidential by nature and cannot be publicly disclosed; this repository demonstrates the same process, documentation standards, and physical-device testing approach applied on real client work, using a fictional app so it can be shared openly as a portfolio piece.*

An end-to-end user acceptance testing (UAT) testware repository showcasing a fully manual approach to mobile app testing, structured to reflect the ISTQB Foundation Level (CTFL v4.0) fundamental test process.

This repository hosts the complete testware suite and execution records for the UAT validation of a fictional ADHD-friendly educational memory-training game, **MemoMatch (Beta, Build V 20260518)**.

The primary objective of testing was to ensure a stable, calm, zero-stall user experience. Because the app targets children, teenagers, and adults with ADHD, software defects such as erratic audio, sudden animation flashes, or broken progression screens represent a high risk of sensory overstimulation and loss of user focus — so sensory and interruption-handling stability were treated as first-class quality objectives throughout this cycle.

## Contents
- [Physical Device & Environment Matrix](#physical-device--environment-matrix)
- [Test Process Documentation Structure](#test-process-documentation-structure)
- [Validation Methodologies & Test Quality Metrics](#validation-methodologies--test-quality-metrics)
- [Active Test Cycle Insights](#active-test-cycle-insights)
- [About the QA Professional](#about-the-qa-professional)

---

## Physical Device & Environment Matrix
Testing was conducted strictly on a physical Android device to expose real hardware behavior that emulators cannot fully replicate.

* **Device:** Samsung Galaxy S21 FE 5G | Model: `SM-G990E/DS` | Android 16 (One UI 8.0)

---

## Test Process Documentation Structure
The repository is organized into sequential testing phases to maintain a clear, auditable execution record:

```text
├── README.md
├── 01_Test_planning/
│   └── MemoMatch_Test_Plan_TP-MOB-02_v1.2.md
├── 02_Test_analysis/
│   ├── MemoMatch_RTM-MOB-02_v1.1.md
│   └── MemoMatch_Test_Conditions_TCOND-MOB-02_v1.0.md
├── 03_Test_design/
│   └── MemoMatch_Test_Cases_Suite_TC-MOB-02_v1.1.md
├── 04_Test_implementation/
│   └── MemoMatch_Test_Procedures_TPROC-MOB-02_v1.1.md
├── 05_Test_execution/
│   ├── MemoMatch_Execution_Log_EL-MOB-02_v1.1.md
│   ├── MemoMatch_Defect_Report_BUG-MOB-02-01.md
│   ├── MemoMatch_Defect_Report_BUG-MOB-02-02.md
│   ├── MemoMatch_Defect_Report_BUG-MOB-02-03.md
│   ├── MemoMatch_Defect_Report_BUG-MOB-02-04.md
│   └── voice-speed-slider-usability.jpg
└── 06_Test_completion/
    └── MemoMatch_Test_Report_TSR-MOB-02_v1.1.md
```

**Note:** `TCOND-MOB-02` (Test Conditions) is a new addition to this project's documentation — the original set linked requirements directly to test cases with no Test Analysis artifact in between. It's filed under `02_Test_analysis` alongside the RTM, consistent with where Test Conditions sit in the Corvex Packaging and TrueString Tuner portfolio pieces.

---

## Validation Methodologies & Test Quality Metrics
* **Specification-Based Techniques (EP & BVA):** Applied Equivalence Partitioning (EP) and Boundary Value Analysis (BVA) to verify numerical boundaries and system configurations, including point redemption tiers, custom input field limits, audio volume constraints (0–100%), and grid size configurations (ranging from 1/4 to 4/16 layout ratios) using decks such as "Colors" and "Country Balls."
* **State Transition Testing:** Evaluated the behavioral logic of dynamic UI elements by tracing explicit state transitions — card lifecycle states (face-down, flipped/active, matched/mismatched pairs) alongside global application state transitions, including level progression, ad-triggering intervals, and premium content lockouts.
* **Usability & Configuration Resilience:** Verified interface responsiveness, localization switching (English UK vs. English US), and visual asset scaling. Isolated critical UI defects — including non-linear slider scales and freezes during the Guided Tour workflow — to help ensure interface stability.
* **Non-Functional & Interruption Adaptability:** Tested application resilience against real-world interruptions and edge-case behaviors, including game-state recovery under abrupt hardware interruptions (incoming calls, app minimization) and input handling under simultaneous high-frequency card-tapping.
* **Defect Traceability & RTM:** Maintained full requirement-to-defect traceability via `RTM-MOB-02`, mapping in-scope requirements down to test conditions, test cases, and defect logs (`BUG-MOB-02-01` through `BUG-MOB-02-04`).

---

## Active Test Cycle Insights
* **Requirements Coverage (in-scope):** 28 / 28 (100%)
* **Test Cases Executed:** 21 / 21 (100%)
* **Test Case Pass Rate:** 80.95% (17 Pass, 4 Fail) — below the Test Plan's 95% exit criterion
* **Open Defects:** 4 (2 High, 1 Medium, 1 Low severity)
* **Deployment Release Status:** **Rejected** — see `TSR-MOB-02` for the full exit-criteria evaluation and recommendation.

### Defects Summary
| Defect ID | Description | Severity | Priority | Status |
| :--- | :--- | :--- | :--- | :--- |
| `BUG-MOB-02-01` | App hangs on 7th Tour screen, forcing a hard application termination | High | Medium | Open |
| `BUG-MOB-02-02` | False "offline" warning banner triggers during active gameplay | Medium | High | Open |
| `BUG-MOB-02-03` | Logic mini-game progression blocked after second problem | High | High | Open |
| `BUG-MOB-02-04` | Speech speed slider lacks a 100% snap-point | Low | Medium | Open |

*Severity reflects technical/functional impact; Priority reflects business urgency to fix — per the [ISTQB Glossary](https://istqb-glossary.page/), these are assessed independently rather than interchangeably. This project uses a three-tier High/Medium/Low severity scale, as originally authored.*

---

## About the QA Professional
I am an **ISTQB® Certified Freelance Software Tester** specializing in end-to-end **User Acceptance Testing (UAT)** and digital quality assurance. I partner with businesses to validate and optimize high-impact digital products before market launch, ensuring seamless user experiences and functional reliability across multiple platforms.

### Core Areas of Expertise:
* **Mobile Application Testing:** Native Android app validation, physical device matrix testing, hardware-software interaction testing, and interruption handling.
* **E-Commerce Platforms:** End-to-end checkout flow validation, shopping cart state persistence, search engine routing parameters, and localized user journey verification.
* **Web Application QA:** Cross-browser compatibility validation, responsive web design (RWD) testing, BDD automation framework assembly, and functional regression testing.

### Let's Connect:
* **LinkedIn:** [Annalie Prinsloo](https://www.linkedin.com/in/annalieprinsloo001/)
* **Professional Email:** <annalieprinsloo1@gmail.com>
* **ISTQB Verification ID:** [ZA010123GK0981040](https://scr.istqb.org/?name=Annalie+Prinsloo&number=ZA010123GK0981040&orderBy=relevancy&orderDirection=&dateStart=&dateEnd=&expiryStart=&expiryEnd=&certificationBody=&examProvider=&certificationLevel=&country=)
* **Availability:** Open to contract, freelance QA opportunities.
