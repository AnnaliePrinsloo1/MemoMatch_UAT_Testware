# Requirements Traceability Matrix (RTM)

**Identifier:** RTM-MOB-02  
**Version:** v1.1  
**Test Basis:** Functional Scope & Requirements (MemoMatch Test Plan: TP-MOB-02)  
**Status:** Completed  
**Date:** 2026-09-10  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-05-22 | Annalie Prinsloo | Baseline RTM. |
| 1.1 | 2026-09-10 | Annalie Prinsloo | Fictionalized; identifiers migrated to `*-MOB-02` convention (`REQ_xx_00` → `REQ-xx-00`, `TC_xx_000` → `TC-xx-00`); added the missing Test Condition layer (`TCOND-MOB-02`); corrected two rows (`REQ-MM-02`, `REQ-MM-05`) that were marked "Covered" despite the linked feature being explicitly out-of-scope per `TP-MOB-02` §3.3, and despite their cited test cases not actually exercising them; fixed a typo (`TTC_FLOW_004` → `TC-FLOW-04`); added a section for test coverage that doesn't cleanly trace to a single predefined requirement. |

---

## 2. Traceability Ledger
| Req ID | Requirement Category | Requirement Description | Test Condition ID | Test Case ID | Execution Status | Related Defect ID(s) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **`REQ-MM-01`** | Main Menu | Provide a choice of background music from a list of 16 tracks. | `TCOND-MM-01` | `TC-MM-01`, `TC-CUST-01` | Fail | **`BUG-MOB-02-01`**, **`BUG-MOB-02-02`** |
| **`REQ-MM-02`** | Main Menu | Display a Daily Brain Bite random fact check system. | N/A | N/A | **Out of Scope** (excluded per `TP-MOB-02` §3.3) | N/A |
| **`REQ-MM-03`** | Main Menu | Offer help folders containing written topic information. | `TCOND-MM-03` | `TC-SET-02` | Pass | N/A |
| **`REQ-MM-04`** | Main Menu | Redeem points field accepting small, large, or empty inputs. | `TCOND-MM-04` | `TC-RED-01` | Pass | N/A |
| **`REQ-MM-05`** | Main Menu | Premium storefront for tokens, lives, and virtual coffee. | N/A | N/A | **Out of Scope** (excluded per `TP-MOB-02` §3.3) | N/A |
| **`REQ-MM-06`** | Main Menu | Outbound links for external legal docs (Privacy & EULA). | `TCOND-MM-06` | `TC-MM-02` | Pass | N/A |
| **`REQ-MM-07`** | Main Menu | Guided app tour with an instant audio narration toggle. | `TCOND-MM-07` | `TC-MM-01` | Fail | **`BUG-MOB-02-01`** |
| **`REQ-GS-01`** | Game Selection | Allow choice of 14 decks distributed across 3 main topics. | `TCOND-GS-01` | `TC-SET-01` | Pass | N/A |
| **`REQ-GS-02`** | Game Selection | Configure pair counts and levels (e.g., 1/4, 2/6 grids). | `TCOND-GS-02` | `TC-SET-01` | Pass | N/A |
| **`REQ-GS-03`** | Game Selection | Support 10 languages (including US and UK English). | `TCOND-GS-03` | `TC-SET-04` | Pass | N/A |
| **`REQ-GS-04`** | Game Selection | Content sub-tabs for regional sorting (All, Africa, etc.). | `TCOND-GS-04` | `TC-SET-02` | Pass | N/A |
| **`REQ-GS-05`** | Game Selection | Provide Regular mode and Time Trial game modes. | `TCOND-GS-05` | `TC-SET-03` | Pass | N/A |
| **`REQ-GS-06`** | Game Selection | Choose card back designs to be identical or distinct. | `TCOND-GS-06` | `TC-GAME-06` | Pass | N/A |
| **`REQ-GS-07`** | Game Selection | Info icon displaying Game Values and game filters text. | `TCOND-GS-07` | `TC-SET-02` | Pass | N/A |
| **`REQ-MP-01`** | Multiplayer | Restrict multiplayer live duels to Premium tier accounts. | `TCOND-MP-01` | `TC-FLOW-04` | Pass | N/A |
| **`REQ-LB-01`** | Leaderboard | Show top 3 leaders per game with an expanded full view. | `TCOND-LB-01` | `TC-FLOW-01` | Pass | N/A |
| **`REQ-CZ-01`** | Customization | Adjust narration/speech speed via a sliding bar. | `TCOND-CZ-01` | `TC-CUST-01` | Fail | **`BUG-MOB-02-04`** |
| **`REQ-CZ-02`** | Customization | Adjust master volume levels via a smooth sliding bar. | `TCOND-CZ-02` | `TC-CUST-01` | Pass | N/A |
| **`REQ-CZ-03`** | Customization | Switch age modes (Child logic puzzles vs Adult quizzes). | `TCOND-CZ-03` | `TC-CUST-02` | Pass | N/A |
| **`REQ-CZ-04`** | Customization | Choose avatar graphics from 8 animal selection assets. | `TCOND-CZ-04` | `TC-MM-01` | Pass | N/A |
| **`REQ-GP-01`** | Gameplay | Track and duplicate active card to top-bar display layout. | `TCOND-GP-01` | `TC-GAME-01` | Pass | N/A |
| **`REQ-GP-02`** | Gameplay | Provide a Lightbulb hint tool that briefly exposes a pair. | `TCOND-GP-02` | `TC-GAME-04` | Pass | N/A |
| **`REQ-GP-03`** | Gameplay | Provide a Graduation cap icon revealing detailed facts of active cards. | `TCOND-GP-03` | `TC-GAME-05` | Pass | N/A |
| **`REQ-GP-04`** | Gameplay | Matching pairs (=) vanish; support manual/auto close. | `TCOND-GP-04` | `TC-GAME-02` | Pass | N/A |
| **`REQ-GP-05`** | Gameplay | Mismatched cards (!=) flash briefly and turn face-down. | `TCOND-GP-05` | `TC-GAME-03` | Pass | N/A |
| **`REQ-GP-06`** | Gameplay | Display performance metrics in a final Result Window. | `TCOND-GP-06` | `TC-FLOW-01` | Pass | N/A |
| **`REQ-GP-07`** | Gameplay | Show ads between levels for free tier users. | `TCOND-GP-07` | `TC-FLOW-03` | Fail | **`BUG-MOB-02-02`** |
| **`REQ-GP-08`** | Gameplay | Bottom status row showing level success by card back type. | `TCOND-GP-08` | `TC-FLOW-01` | Pass | N/A |
| **`REQ-GP-09`** | Gameplay | Quick-action bottom controls (Replay level, Next level). | `TCOND-GP-09` | `TC-FLOW-02` | Pass | N/A |
| **`REQ-NF-01`** | Non-Functional | App state preservation during app minimization. | `TCOND-NF-01` | `TC-NEG-01` | Pass | N/A |

---

## 3. Additional Test Coverage Not Traced to a Single Predefined Requirement
Two items surfaced during execution that don't cleanly map to a single requirement in the ledger above:

| Item | Source | Notes |
| :--- | :--- | :--- |
| `TC-NEG-02` (simultaneous card-tap protection) | Test Cases Suite | Executed and passed, but no formal requirement in the original 30-item specification covers input-debouncing behavior. Recommend a formal requirement be added in a future backlog refinement. |
| **`BUG-MOB-02-03`** (mini-game progression blocked after 2nd problem) | Found via `TC-CUST-02` | `REQ-CZ-03` only specifies that age-mode switching displays the correct puzzle type (Child logic puzzle vs. Adult quiz) — which it does. The deeper mini-game progression mechanic that fails here isn't described by any formal requirement. Recommend logging a dedicated requirement for interstitial mini-game progression in a future backlog refinement. |

---

## 4. Verification Metrics Summary
* **Total requirements defined:** 30
* **Requirements in scope:** 28
* **Requirements out of scope (excluded per `TP-MOB-02` §3.3):** 2 (`REQ-MM-02`, `REQ-MM-05`)
* **In-scope requirement coverage:** 28 / 28 (100%)
* **Total test conditions defined:** 28
* **Test conditions passed:** 24 / 28 (85.7%)
* **Test conditions failed:** 4 / 28 (14.3%) — `TCOND-MM-01`, `TCOND-MM-07`, `TCOND-CZ-01`, `TCOND-GP-07`
* **Unmapped requirements:** 0 (within scope)
