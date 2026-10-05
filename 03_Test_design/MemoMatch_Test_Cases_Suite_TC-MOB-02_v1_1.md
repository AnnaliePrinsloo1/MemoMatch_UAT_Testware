# Test Design: Manual Test Cases Suite

**Identifier:** TC-MOB-02  
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
| 1.0 | 2026-05-22 | Annalie Prinsloo | Baseline manual test cases suite. |
| 1.1 | 2026-09-10 | Annalie Prinsloo | Fictionalized; Test Case IDs renamed `TC_xx_000` → `TC-xx-00`; converted from wide-table format to the standard field-based template (Description / Target Test Condition / Preconditions / Test Data Category / Expected Result / Priority); detailed step-by-step scripts moved to `TPROC-MOB-02` to avoid duplicating content across two documents. |

---

## 2. High-Level Test Suite Overview
This test suite defines the concrete manual test cases for the UAT phase of the MemoMatch App (Beta). Test cases are structured to validate both standard functionality and the app's ADHD-friendly requirements — sensory management, predictable interruption handling, and low-stimulation flows. All test cases execute on the single target device defined in `TP-MOB-02` §4 (Samsung Galaxy S21 FE 5G, Android 16).

---

## 3. Test Suite 1: Main Menu & Customization (Sensory & Accessibility)

### TC-MM-01: Guided Tour Functionality and Narration Toggle
* **Description:** Verify the Guided Tour opens correctly, audio narration toggles instantly, and screen navigation is smooth. Also exercises avatar selection, which is reachable from the same Main Menu flow.
* **Target Test Condition:** `TCOND-MM-01`, `TCOND-MM-07`, `TCOND-CZ-04`
* **Preconditions:** App is freshly installed, or the Tour is launched from the Main Menu; device audio is on and audible.
* **Test Data Category:** Speaker toggle state (ON/OFF); avatar selection from 8 animal graphics; background music track selection from 16 tracks.
* **Expected Result:** The tour opens without lag, narration plays instantly when toggled ON and stops instantly when toggled OFF, navigation arrows respond smoothly, and avatar/music selections apply correctly.
* **Priority:** High

### TC-MM-02: Redirection of Legal Documents
* **Description:** Verify that Legal Docs links (Privacy Policy, EULA) open the correct external URLs and return cleanly to the app.
* **Target Test Condition:** `TCOND-MM-06`
* **Preconditions:** User is on the Main Menu screen; device has an active internet connection and a default browser installed.
* **Test Data Category:** Privacy Policy and EULA link targets.
* **Expected Result:** Both links open the correct external URL in the browser; the user returns to the app without crashes or state loss.
* **Priority:** Medium

### TC-CUST-01: Speech Speed and Sound Volume Sliders
* **Description:** Verify both accessibility sliders (speech speed, master volume) move smoothly and apply correctly.
* **Target Test Condition:** `TCOND-MM-01`, `TCOND-CZ-01`, `TCOND-CZ-02`
* **Preconditions:** User is on the Customize settings screen; device audio is enabled.
* **Test Data Category:** Speech speed range (60%–200%, baseline 100%); master volume range (0%–100%).
* **Expected Result:** Both sliders move smoothly without stuttering; narration speed and playback volume dynamically match the selected slider position.
* **Priority:** High

### TC-CUST-02: Age Declaration Mode Switching (Child vs. Adult)
* **Description:** Verify that toggling between Child mode and Adult mode correctly changes the post-level puzzle type shown to the player.
* **Target Test Condition:** `TCOND-CZ-03`
* **Preconditions:** User is on the Customize settings screen.
* **Test Data Category:** Age Declaration toggle state (Child / Adult).
* **Expected Result:** Child mode surfaces a logic puzzle after level completion; Adult mode surfaces a bonus quiz after level completion.
* **Priority:** High

### TC-RED-01: Boundary Value Analysis on Point Redemption
* **Description:** Verify the Redeem Points field correctly handles empty, small-valid, and excessively large inputs.
* **Target Test Condition:** `TCOND-MM-04`
* **Preconditions:** User is on the Redeem Points menu field; the account has a known, valid points balance.
* **Test Data Category:** Empty string; small valid integer (e.g., 1); excessively large integer (e.g., 9999999999).
* **Expected Result:** Empty submission is blocked with a clear validation error; small valid input redeems successfully; excessively large input is rejected without crashing the app.
* **Priority:** Medium

---

## 4. Test Suite 2: Game Setup & Configuration

### TC-SET-01: Deck and Level/Pair Selection Logic
* **Description:** Verify deck selection and grid/pair configuration load correctly.
* **Target Test Condition:** `TCOND-GS-01`, `TCOND-GS-02`
* **Preconditions:** User is on the Game Selection screen.
* **Test Data Category:** 14 available decks; grid ratios 1/4, 2/6, 3/8, and 4/16.
* **Expected Result:** The game loads with the chosen deck theme, and the grid size matches the selected level/pair configuration.
* **Priority:** High

### TC-SET-02: Content Filters (Geographic/General)
* **Description:** Verify content/regional filters correctly isolate deck categories, and that the info icon displays correct supplementary text.
* **Target Test Condition:** `TCOND-MM-03`, `TCOND-GS-04`, `TCOND-GS-07`
* **Preconditions:** User is on the Game Selection screen, focused on the "Country Balls" deck.
* **Test Data Category:** Region filters: All, Africa, America, Asia, Europe.
* **Expected Result:** Deck choices filter instantly to the active region; the info icon correctly displays Game Values and filter text; help folders open with correct topic content.
* **Priority:** Medium

### TC-SET-03: Game Mode Switching (Regular vs. Time Trial)
* **Description:** Verify Regular mode and Time Trial mode both function as designed.
* **Target Test Condition:** `TCOND-GS-05`
* **Preconditions:** User is on the Game Selection screen.
* **Test Data Category:** Mode toggle: Regular / Time Trial.
* **Expected Result:** Regular mode tracks turns/time without pressure limits; Time Trial mode introduces a visible countdown timer.
* **Priority:** High

### TC-SET-04: Localization Functionality (UK vs. US English)
* **Description:** Verify UI text localizes correctly between English UK and English US without layout breakage.
* **Target Test Condition:** `TCOND-GS-03`
* **Preconditions:** User is on the Language Selection menu.
* **Test Data Category:** Language options: English US, English UK.
* **Expected Result:** Text localizes correctly (e.g., "Color" vs. "Colour"); no overlapping text or UI breaking occurs.
* **Priority:** Low

---

## 5. Test Suite 3: Core Gameplay & Memory Mechanics

### TC-GAME-01: Card Selection and UI Helper Tracking
* **Description:** Verify tapping a card flips it and duplicates its image into the top navbar tracking display.
* **Target Test Condition:** `TCOND-GP-01`
* **Preconditions:** Game level is launched.
* **Test Data Category:** Single card tap interaction.
* **Expected Result:** Card flips to reveal content; card image duplicates cleanly into the "Selected card" placeholder window.
* **Priority:** High

### TC-GAME-02: Matching Pairs Logic (=) and Close Settings
* **Description:** Verify matching-pair detection and the manual/auto-close behavior of the pair confirmation window.
* **Target Test Condition:** `TCOND-GP-04`
* **Preconditions:** Game level is launched; customization set to "Manual close."
* **Test Data Category:** Two identical/matching cards.
* **Expected Result:** Pair window shows match (=) status; cards disappear from the field; window remains until manually dismissed.
* **Priority:** High

### TC-GAME-03: Non-Matching Pairs Logic (!=) and Card Flashing
* **Description:** Verify mismatched-pair detection and the visual flash/reset behavior.
* **Target Test Condition:** `TCOND-GP-05`
* **Preconditions:** Game level is launched.
* **Test Data Category:** Two different, non-matching cards.
* **Expected Result:** Window shows mismatch (!=) status; non-matching cards briefly flash; cards return face-down to original positions.
* **Priority:** High

### TC-GAME-04: Hint Functionality (Lightbulb Icon)
* **Description:** Verify the Lightbulb hint tool briefly exposes a matching pair without destabilizing game state.
* **Target Test Condition:** `TCOND-GP-02`
* **Preconditions:** Game level is actively running.
* **Test Data Category:** Lightbulb icon tap.
* **Expected Result:** App briefly flashes/reveals a matching pair; overall game state remains stable.
* **Priority:** Medium

### TC-GAME-05: Card Info View (Graduation Cap Icon)
* **Description:** Verify the Graduation Cap icon opens an educational-facts overlay for the cards in play.
* **Target Test Condition:** `TCOND-GP-03`
* **Preconditions:** Game level is actively running.
* **Test Data Category:** Graduation Cap icon tap.
* **Expected Result:** Overlay opens showing the cards in play with additional educational facts.
* **Priority:** Medium

### TC-GAME-06: Back Side Icon Variations (Same vs. Different)
* **Description:** Verify face-down card designs correctly reflect the "Same" vs. "Different" back-side setting.
* **Target Test Condition:** `TCOND-GS-06`
* **Preconditions:** Game selection set to "Different" back sides.
* **Test Data Category:** Back-side setting: Same / Different.
* **Expected Result:** "Different" mode shows unique helper icons per pair; "Same" mode shows uniform identical icons.
* **Priority:** High

---

## 6. Test Suite 4: End of Level & Flow Transitions

### TC-FLOW-01: Level Completion and Result Window
* **Description:** Verify the Result Window, bottom-row level tracking, and leaderboard display correctly at level completion.
* **Target Test Condition:** `TCOND-LB-01`, `TCOND-GP-06`, `TCOND-GP-08`
* **Preconditions:** User matches the final pair on the board.
* **Test Data Category:** Completed level metrics (turn count, clear time); leaderboard top-3 entries.
* **Expected Result:** Result window appears with turn counts and clear time; bottom row updates with a coloured field for the completed level; leaderboard shows top 3 with a working expanded view.
* **Priority:** High

### TC-FLOW-02: Replay and Next Level Progression Buttons
* **Description:** Verify the Replay and Next Level quick-action controls function correctly.
* **Target Test Condition:** `TCOND-GP-09`
* **Preconditions:** User is on the level Result Window.
* **Test Data Category:** Replay arrow tap; Up arrow (next level) tap.
* **Expected Result:** Replay arrow restarts the level with a newly randomized deck; Up arrow safely advances to the next difficulty level.
* **Priority:** High

### TC-FLOW-03: Ad Appearance Between Levels (Free Tier)
* **Description:** Verify an advertisement overlay appears cleanly between levels for free-tier users, without introducing UI side effects.
* **Target Test Condition:** `TCOND-GP-07`
* **Preconditions:** User is on the free version of the app.
* **Test Data Category:** Level completion → Up arrow tap.
* **Expected Result:** An advertisement overlay safely appears between levels without crashing the app or triggering unrelated UI warnings.
* **Priority:** Medium

### TC-FLOW-04: Premium Lockouts (Multiplayer Functionality)
* **Description:** Verify Free Tier accounts are correctly blocked from multiplayer and shown a clear upgrade path.
* **Target Test Condition:** `TCOND-MP-01`
* **Preconditions:** User profile is Free Tier (Non-Premium).
* **Test Data Category:** Multiplayer icon tap; live duel/challenge attempt.
* **Expected Result:** Feature is blocked; user is presented with a clear upgrade path/Premium subscription window.
* **Priority:** High

---

## 7. Non-Functional & Negative Test Cases

### TC-NEG-01: Game State During Sudden Interruptions
* **Description:** Verify game state, timer, and layout are preserved through minimization and interruption events.
* **Target Test Condition:** `TCOND-NF-01`
* **Preconditions:** Game level is actively running.
* **Test Data Category:** App minimization; simulated incoming phone call.
* **Expected Result:** App recovers cleanly; timer pauses instantly on interruption; game state and uncovered card positions are perfectly preserved.
* **Priority:** High

### TC-NEG-02: Simultaneous Card Tapping Protection
* **Description:** Verify the app safely debounces rapid, simultaneous multi-card taps.
* **Target Test Condition:** Not traced to a predefined requirement — see `RTM-MOB-02` §3.
* **Preconditions:** Game level is actively running.
* **Test Data Category:** 3–4 simultaneous rapid card taps.
* **Expected Result:** System processes only the first two inputs cleanly; app UI does not freeze, overlap images, or crash.
* **Priority:** Medium
