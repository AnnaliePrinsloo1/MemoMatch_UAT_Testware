# Test Analysis: Test Conditions

**Identifier:** TCOND-MOB-02  
**Version:** v1.0  
**Test Basis:** Functional Scope & Requirements (MemoMatch Test Plan: TP-MOB-02)  
**Status:** Completed  
**Date:** 2026-09-10  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-09-10 | Annalie Prinsloo | New document. The original documentation set had no Test Analysis artifact — the RTM linked requirements directly to test cases, skipping the Test Condition layer. This document derives 28 test conditions from the 28 in-scope requirements in `RTM-MOB-02`, restoring the standard ISTQB Test Analysis → Test Design → Test Implementation structure. |

---

## 2. Purpose and Methodology
Test conditions in this document define exactly **what** must be verified during the User Acceptance Testing (UAT) phase for the MemoMatch App (Beta, Build V 20260518). These conditions are derived from the 28 in-scope requirements defined in the Test Plan (`TP-MOB-02` §3.2), excluding the two requirements explicitly out of scope per §3.3.

**Priority Matrix:**
* **High:** Core memory-engine mechanics, sensory-safety-adjacent controls (audio sliders, narration), and flows directly tied to the app's ADHD-focused quality objectives.
* **Medium:** Content filtering, secondary menu functions, and ad/progression transitions.
* **Low:** Non-critical localization coverage.

## 3. Test Conditions Inventory
| Condition ID | Source Requirement | Test Condition (What to Test) | Priority |
| :--- | :--- | :--- | :--- |
| **TCOND-MM-01** | `REQ-MM-01` | Verify that the player can choose background music from a list of 16 tracks. | High |
| **TCOND-MM-03** | `REQ-MM-03` | Verify that help folders open and display correct written topic information. | Medium |
| **TCOND-MM-04** | `REQ-MM-04` | Verify that the Redeem Points field correctly accepts valid input and rejects empty/out-of-bounds input. | Medium |
| **TCOND-MM-06** | `REQ-MM-06` | Verify that outbound legal document links (Privacy Policy, EULA) open the correct URLs and return cleanly to the app. | Medium |
| **TCOND-MM-07** | `REQ-MM-07` | Verify that the guided app tour completes without stalling, with an instant audio narration toggle. | High |
| **TCOND-GS-01** | `REQ-GS-01` | Verify that the player can select from 14 decks distributed across 3 main topics. | High |
| **TCOND-GS-02** | `REQ-GS-02` | Verify that pair counts and grid levels (e.g., 1/4, 2/6, 3/8, 4/16) configure correctly. | High |
| **TCOND-GS-03** | `REQ-GS-03` | Verify that supported language selection (English UK, English US) displays correctly localized text. | Low |
| **TCOND-GS-04** | `REQ-GS-04` | Verify that content sub-tabs correctly filter decks by region (All, Africa, America, Asia, Europe). | Medium |
| **TCOND-GS-05** | `REQ-GS-05` | Verify that Regular mode and Time Trial mode both function as designed. | High |
| **TCOND-GS-06** | `REQ-GS-06` | Verify that card back designs correctly render as identical or distinct per the selected setting. | High |
| **TCOND-GS-07** | `REQ-GS-07` | Verify that the info icon displays correct Game Values and game filter text. | Medium |
| **TCOND-MP-01** | `REQ-MP-01` | Verify that Free Tier accounts are correctly blocked from multiplayer and shown a clear upgrade path. | High |
| **TCOND-LB-01** | `REQ-LB-01` | Verify that the leaderboard shows the top 3 leaders per game, with a working expanded view. | High |
| **TCOND-CZ-01** | `REQ-CZ-01` | Verify that the narration/speech speed slider adjusts smoothly and predictably across its full range. | High |
| **TCOND-CZ-02** | `REQ-CZ-02` | Verify that the master volume slider adjusts smoothly and accurately reflects the selected level. | High |
| **TCOND-CZ-03** | `REQ-CZ-03` | Verify that switching between Child mode and Adult mode correctly changes the displayed post-level puzzle type. | High |
| **TCOND-CZ-04** | `REQ-CZ-04` | Verify that the player can select an avatar from 8 animal graphic options. | High |
| **TCOND-GP-01** | `REQ-GP-01` | Verify that tapping a card flips it and duplicates its image into the top navbar tracking display. | High |
| **TCOND-GP-02** | `REQ-GP-02` | Verify that the Lightbulb hint tool briefly exposes a matching pair without destabilizing game state. | Medium |
| **TCOND-GP-03** | `REQ-GP-03` | Verify that the Graduation Cap icon opens an overlay with detailed facts about the active cards. | Medium |
| **TCOND-GP-04** | `REQ-GP-04` | Verify that matching pairs are correctly identified, vanish from the grid, and respect the manual/auto-close setting. | High |
| **TCOND-GP-05** | `REQ-GP-05` | Verify that mismatched cards are correctly flagged, flash briefly, and return face-down. | High |
| **TCOND-GP-06** | `REQ-GP-06` | Verify that the Result Window displays correct performance metrics at level completion. | High |
| **TCOND-GP-07** | `REQ-GP-07` | Verify that ads display correctly between levels for free-tier users, without introducing UI side effects. | Medium |
| **TCOND-GP-08** | `REQ-GP-08` | Verify that the bottom status row correctly reflects level success by card-back type. | High |
| **TCOND-GP-09** | `REQ-GP-09` | Verify that the Replay and Next Level quick-action controls function correctly. | High |
| **TCOND-NF-01** | `REQ-NF-01` | Verify that app state is preserved during minimization and other interruption events. | High |
