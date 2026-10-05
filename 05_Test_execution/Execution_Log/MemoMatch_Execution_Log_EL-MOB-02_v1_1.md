# Test Execution Log

**Identifier:** EL-MOB-02  
**Version:** v1.1  
**Test Basis:** Functional Scope & Requirements (MemoMatch Test Plan: TP-MOB-02)  
**Status:** Completed  
**Date:** 2026-05-20  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-05-20 | Annalie Prinsloo | Baseline execution log. |
| 1.1 | 2026-09-10 | Annalie Prinsloo | Fictionalized; Test Case IDs renamed `TC_xx_000` → `TC-xx-00`; defect IDs renamed `DF_00x` → `BUG-MOB-02-0x`; added the Target Test Condition ID column for traceability with `TCOND-MOB-02`. |

---

## 2. General Metadata
* **Test Cycle:** Beta Sprint 1 - Accessibility & Core Flow
* **Test Environment:**
  * **Device:** Samsung Galaxy S21 FE 5G (Model: SM-G990E/DS)
  * **OS Version:** Android 16 (One UI 8.0)
  * **App Version:** Google Play Beta Build V 20260518
  * **Network Profile:** Stable Wi-Fi (Symmetrical 100Mbps) / Cellular 5G

## 3. Summary Metrics
* **Total Test Cases Planned:** 21
* **Total Test Cases Executed:** 21
* **Passed:** 17
* **Failed:** 4 (`TC-MM-01`, `TC-CUST-01`, `TC-CUST-02`, `TC-FLOW-03` — scored as Fail due to active defects)
* **Blocked:** 0

## 4. Execution Results Table
| Test Case ID | Target Test Condition ID | Test Suite / Focus | Status | Linked Defect ID | Remarks / Observations |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `TC-MM-01` | `TCOND-MM-01`, `TCOND-MM-07`, `TCOND-CZ-04` | Main Menu: Guided Tour | **FAIL** | `BUG-MOB-02-01`, `BUG-MOB-02-02` | UI freezes on 7th tour screen. False offline banner appears. |
| `TC-MM-02` | `TCOND-MM-06` | Main Menu: Legal Docs | **PASS** | None | Redirection to browser is smooth and returns cleanly. |
| `TC-CUST-01` | `TCOND-MM-01`, `TCOND-CZ-01`, `TCOND-CZ-02` | Customization: Sliders | **FAIL** | `BUG-MOB-02-04` | Out-of-bounds inputs blocked correctly. Speech speed slider scale is non-linear. |
| `TC-CUST-02` | `TCOND-CZ-03` | Customization: Age Mode | **FAIL** | `BUG-MOB-02-03` | Logic puzzles displayed correctly in child mode; bonus quiz appears correctly in adult mode. Logic mini-game does not advance past problem 2. |
| `TC-RED-01` | `TCOND-MM-04` | Redeem Points: BVA | **PASS** | None | System throws validation errors where expected. |
| `TC-SET-01` | `TCOND-GS-01`, `TCOND-GS-02` | Setup: Grid Configuration | **PASS** | None | Verified using "Colors" deck at 1/4, 2/6, 3/8, and 4/16 layout ratios. |
| `TC-SET-02` | `TCOND-MM-03`, `TCOND-GS-04`, `TCOND-GS-07` | Setup: Content Filters | **PASS** | None | Verified using "Country Balls" filter configuration. |
| `TC-SET-03` | `TCOND-GS-05` | Setup: Game Modes | **PASS** | None | Verified using Regular mode tracking. |
| `TC-SET-04` | `TCOND-GS-03` | Setup: User Language | **PASS** | None | Verified switching between English UK and English US. |
| `TC-GAME-01` | `TCOND-GP-01` | Gameplay: Card Selection | **PASS** | None | Card selection and UI helper tracking verified. |
| `TC-GAME-02` | `TCOND-GP-04` | Gameplay: Card Matching Pairs | **PASS** | None | Card matching logic verified. |
| `TC-GAME-03` | `TCOND-GP-05` | Gameplay: Card Non-Matching Pairs | **PASS** | None | Card non-matching logic verified. |
| `TC-GAME-04` | `TCOND-GP-02` | Gameplay: Card Hint | **PASS** | None | Flashing matching-cards hint verified. |
| `TC-GAME-05` | `TCOND-GP-03` | Gameplay: Game Information | **PASS** | None | Graduation Cap card-info display verified. |
| `TC-GAME-06` | `TCOND-GS-06` | Gameplay: Card Backs | **PASS** | None | Validated uniform "Same" back vs. "Different" back sides. |
| `TC-FLOW-01` | `TCOND-LB-01`, `TCOND-GP-06`, `TCOND-GP-08` | Flow Transitions: Level Completion and Results Window | **PASS** | None | Validated that the results window appears correctly after level completion, including leaderboard display. |
| `TC-FLOW-02` | `TCOND-GP-09` | Flow Transitions: Replay and Next Level Progression | **PASS** | None | Validated replay and next-level progression functions correctly. |
| `TC-FLOW-03` | `TCOND-GP-07` | Flow Transitions: Ad Appearance | **FAIL** | `BUG-MOB-02-02` | Ads do appear, but the false offline warning banner appears simultaneously. |
| `TC-FLOW-04` | `TCOND-MP-01` | Flow Transitions: Premium Lockout | **PASS** | None | Verified premium lockout blocks multiplayer access. |
| `TC-NEG-01` | `TCOND-NF-01` | Non-Functional: Game State Interruption | **PASS** | None | Verified that game state recovers correctly. |
| `TC-NEG-02` | Not traced — see `RTM-MOB-02` §3 | Non-Functional: Simultaneous Card Tapping | **PASS** | None | Verified that only the first two simultaneous inputs are processed. |
