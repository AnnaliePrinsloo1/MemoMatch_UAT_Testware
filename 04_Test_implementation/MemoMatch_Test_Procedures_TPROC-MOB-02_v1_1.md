# Test Implementation: Test Procedures & Execution Scripts

**Identifier:** TPROC-MOB-02  
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
| 1.0 | 2026-05-22 | Annalie Prinsloo | Baseline test procedures. |
| 1.1 | 2026-09-10 | Annalie Prinsloo | Fictionalized; procedures assigned dedicated `TPROC-xx-00` identifiers (previously procedures were headed only by their Test Case ID); converted from prose numbered-list format to the standard step-table format; corrected the systematic "desks" → "decks" typo. |

---

## 2. Pre-Execution Setup & Environmental Verification Checklist
### Preconditions
* The tester has access to the target test device (Samsung Galaxy S21 FE 5G).
* The device has a stable network connection to pull the latest beta build.

### Procedure
1. Open the device settings and verify that the Google Play Beta app version accurately matches the target build release number.
2. Open the device's system tray/recent apps view and clear all background applications from the RAM.
3. Open the device system settings menu on the S21 FE, navigate to battery configurations, and completely disable all active battery-saver profiles.

### Expected Results
* The installed application build matches the staging environment requirements exactly.
* The system RAM is completely clear of background app processes to avoid performance interference.
* Battery-saving background restrictions are turned off, preventing premature background freezing or execution throttling during interruptions.

---

## 3. Test Procedure Suite

### TPROC-MM-01: Guided Tour Functionality and Narration Toggle
* **Associated Test Case:** `TC-MM-01`
* **Environmental Setup Steps:** App is freshly installed, or the Guided Tour is launched from the Main Menu. Device audio is on and set to an audible level.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Launch the app and navigate to the Main Menu. | Menu Interaction | Main Menu renders cleanly. |
| 2 | Tap the Tour button. | Button Tap | Guided Tour opens immediately without lag. |
| 3 | Toggle the Speaker icon to ON and listen for 5 seconds. | Speaker Toggle: ON | Clear audio narration plays. |
| 4 | Tap the Right Arrow, then the Left Arrow. | Navigation Arrows | Screen transitions are smooth and responsive. |
| 5 | Toggle the Speaker icon to OFF. | Speaker Toggle: OFF | Audio narration stops immediately. |

---

### TPROC-MM-02: Redirection of Legal Documents
* **Associated Test Case:** `TC-MM-02`
* **Environmental Setup Steps:** User is on the Main Menu screen. Device has an active internet connection and a default browser installed.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Legal Docs button on the Main Menu. | Button Tap | Legal Docs menu opens. |
| 2 | Tap the Privacy Policy option; observe and verify the opened URL. | Link Tap | External browser opens to the correct Privacy Policy URL. |
| 3 | Return to the app; tap the EULA option; verify the opened URL. | Link Tap | External browser opens to the correct EULA URL. |
| 4 | Return to the application. | Back Navigation | App returns without crashes or state loss. |

---

### TPROC-CUST-01: Speech Speed and Sound Volume Sliders
* **Associated Test Case:** `TC-CUST-01`
* **Environmental Setup Steps:** User is on the Customize settings screen. Device audio is enabled.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Drag the Speech Speed slider to its minimum value. | Slider: Min | Narration speech rate changes to the slowest setting. |
| 2 | Drag the Speech Speed slider to its maximum value. | Slider: Max | Narration speech rate changes to the fastest setting. |
| 3 | Drag the Sound Volume slider to the 100% mark (scale runs 60%–200%). | Slider: 100% | Audio playback volume matches the slider position. |
| 4 | Trigger an in-tour audio prompt. | Audio Prompt | Both sliders move smoothly without stuttering or freezing throughout. |

---

### TPROC-CUST-02: Age Declaration Mode Switching (Child vs. Adult)
* **Associated Test Case:** `TC-CUST-02`
* **Environmental Setup Steps:** User is on the Customize settings screen.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Toggle the Age Declaration setting to Child mode. | Toggle: Child | App updates to the Child layout. |
| 2 | Navigate back to the game, start a match, and complete the level. | Gameplay | A child-friendly logic puzzle appears after level completion. |
| 3 | Return to the Customize screen; toggle Age Declaration to Adult mode. | Toggle: Adult | App updates to the Adult layout. |
| 4 | Return to the game, start a match, and complete the level. | Gameplay | A mature bonus quiz appears after level completion. |

---

### TPROC-RED-01: Boundary Value Analysis on Point Redemption
* **Associated Test Case:** `TC-RED-01`
* **Environmental Setup Steps:** User is on the Redeem Points menu field. The account has a known, valid points balance.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Leave the code field empty and tap Redeem. | Empty Input | Submission blocked; clear validation error displayed. |
| 2 | Enter a small valid integer code (e.g., 1) and tap Redeem. | Input: 1 | Points balance updates successfully. |
| 3 | Enter an excessively large number (e.g., 9999999999) and tap Redeem. | Input: 9999999999 | Validation rejection occurs without crashing the app. |

---

### TPROC-SET-01: Deck and Level/Pair Selection Logic
* **Associated Test Case:** `TC-SET-01`
* **Environmental Setup Steps:** User is on the Game Selection screen.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Select one deck theme from the 14 available options. | Deck Selection | Deck theme is applied. |
| 2 | Choose a level/pair configuration layout (1/4, 2/6, 3/8, or 4/16). | Grid Ratio Selection | Grid configuration is applied. |
| 3 | Tap the button to launch the game. | Launch | Game loads with the chosen deck theme and matching grid size. |

---

### TPROC-SET-02: Content Filters (Geographic/General)
* **Associated Test Case:** `TC-SET-02`
* **Environmental Setup Steps:** User is on the Game Selection screen, focused on the "Country Balls" deck.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Contents tab. | Tab Tap | Contents filter panel opens. |
| 2 | Sequentially toggle through All, Africa, America, Asia, and Europe. | Filter Selection | Deck choices filter instantly to the active region each time. |
| 3 | Tap the info icon. | Icon Tap | Correct Game Values and filter text display. |

---

### TPROC-SET-03: Game Mode Switching (Regular vs. Time Trial)
* **Associated Test Case:** `TC-SET-03`
* **Environmental Setup Steps:** User is on the Game Selection screen.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Select Regular mode and launch the match. | Mode: Regular | Turns/time tracked without pressure limits. |
| 2 | Interact with the gameplay field, then exit to the Game Selection menu. | Exit | Returns cleanly to menu. |
| 3 | Select Time Trial mode and launch the match. | Mode: Time Trial | A clear, visible countdown timer starts. |

---

### TPROC-SET-04: Localization Functionality (UK vs. US English)
* **Associated Test Case:** `TC-SET-04`
* **Environmental Setup Steps:** User is on the Language Selection menu.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Select English US and check textual phrasing throughout the interface. | Language: US | Text displays in US spelling/phrasing. |
| 2 | Select English UK and check textual phrasing throughout the interface. | Language: UK | Text displays in UK spelling/phrasing (e.g., "Colour"); no clipping or overlap. |

---

### TPROC-GAME-01: Card Selection and UI Helper Tracking
* **Associated Test Case:** `TC-GAME-01`
* **Environmental Setup Steps:** A gameplay level is launched and actively running.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap a single face-down card on the grid. | Card Tap | Card flips face-up without latency. |
| 2 | Observe the top navigation bar. | Visual Check | A replica of the card image appears in the "Selected card" placeholder. |

---

### TPROC-GAME-02: Matching Pairs Logic (=) and Close Settings
* **Associated Test Case:** `TC-GAME-02`
* **Environmental Setup Steps:** A gameplay level is running; customization is set to Manual close.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap two matching, identical cards in sequence. | Card Selection | Selected Pair window shows match (=) status. |
| 2 | Observe the field. | Visual Check | Both matched cards disappear cleanly from the grid. |
| 3 | Tap to manually dismiss the pair window. | Dismiss Tap | Window stays visible until manually dismissed, per the Manual close setting. |

---

### TPROC-GAME-03: Non-Matching Pairs Logic (!=) and Card Flashing
* **Associated Test Case:** `TC-GAME-03`
* **Environmental Setup Steps:** A gameplay level is launched and actively running.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap two different, non-matching cards in sequence. | Card Selection | Selected Pair window shows mismatch (!=) status. |
| 2 | Observe the field. | Visual Check | Mismatched cards briefly flash, then return face-down to their original positions. |

---

### TPROC-GAME-04: Hint Functionality (Lightbulb Icon)
* **Associated Test Case:** `TC-GAME-04`
* **Environmental Setup Steps:** A gameplay level is launched and actively running.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Lightbulb hint icon on the top navbar. | Icon Tap | App briefly flashes/reveals a matching pair; game state remains stable. |

---

### TPROC-GAME-05: Card Info View (Graduation Cap Icon)
* **Associated Test Case:** `TC-GAME-05`
* **Environmental Setup Steps:** A gameplay level is launched and actively running.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Graduation Cap icon on the top navbar. | Icon Tap | Info overlay slides into view showing active cards with educational facts. |
| 2 | Review the card details. | Visual Check | Details are accurate and legible. |

---

### TPROC-GAME-06: Back Side Icon Variations (Same vs. Different)
* **Associated Test Case:** `TC-GAME-06`
* **Environmental Setup Steps:** Game selection parameter for card backing is set to "Different."

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Start the match and inspect the face-down card designs. | Backing: Different | Face-down cards display unique helper designs per pair. |
| 2 | Quit, go to settings, toggle to "Same" back sides, and restart. | Backing: Same | Face-down cards display a uniform, identical backing pattern. |

---

### TPROC-FLOW-01: Level Completion and Result Window
* **Associated Test Case:** `TC-FLOW-01`
* **Environmental Setup Steps:** User is in an active match and flips the final matching pair.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Match the final pair to complete the level. | Final Match | Level completes. |
| 2 | Review the Result Window. | Visual Check | Finalized turn counts and clear time display. |
| 3 | Inspect the Bottom Row tracking layout. | Visual Check | Bottom row fills in a distinct coloured field for the completed level. |
| 4 | Check the leaderboard. | Visual Check | Top 3 leaders display, with a working expanded view. |

---

### TPROC-FLOW-02: Replay and Next Level Progression Buttons
* **Associated Test Case:** `TC-FLOW-02`
* **Environmental Setup Steps:** User has completed a level and is on the Result Window.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Replay Arrow. | Button Tap | Level restarts immediately with a newly randomized deck. |
| 2 | Finish the level again, then tap the Up Arrow. | Button Tap | App advances to the next sequential difficulty tier. |

---

### TPROC-FLOW-03: Ad Appearance Between Levels (Free Tier)
* **Associated Test Case:** `TC-FLOW-03`
* **Environmental Setup Steps:** Active user profile is bound to the Free version tier.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Complete all matches to finish the current level. | Level Completion | Level completes cleanly. |
| 2 | Tap the Up Arrow to progress. | Button Tap | A full-screen ad overlay displays between levels without app crashes or unrelated UI warnings. |

---

### TPROC-FLOW-04: Premium Lockouts (Multiplayer Functionality)
* **Associated Test Case:** `TC-FLOW-04`
* **Environmental Setup Steps:** Active user profile is configured as Free Tier.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the Multiplayer icon on the bottom navigation bar. | Icon Tap | Multiplayer feature blocks access immediately. |
| 2 | Try to initiate a live duel challenge match or online queue. | Match Attempt | Matchmaking refuses to launch; a clear subscription pop-up appears. |

---

### TPROC-NEG-01: Game State During Sudden Interruptions
* **Associated Test Case:** `TC-NEG-01`
* **Environmental Setup Steps:** A gameplay level is launched, actively running, with the timer ticking.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Minimize the application during active play. | Minimize | App backgrounds cleanly. |
| 2 | Simulate a system event (e.g., incoming phone call). | Interruption Event | Timer pauses immediately at the moment of interruption. |
| 3 | Maximize and re-open the application. | Restore | App restores cleanly without freezing or crashing; game state and uncovered card positions are perfectly preserved. |

---

### TPROC-NEG-02: Simultaneous Card Tapping Protection
* **Associated Test Case:** `TC-NEG-02`
* **Environmental Setup Steps:** A gameplay level is launched and actively running.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Use multiple fingers to rapidly tap 3–4 cards simultaneously. | Multi-Tap | System processes only the first two inputs cleanly; UI stays functional with no freezes, overlaps, or crashes. |
