## Defect Report: BUG-MOB-02-02

### 1. Summary Information
* **Defect ID:** BUG-MOB-02-02  
* **Title:** False "Looks like you're offline" warning banner triggers during active gameplay  
* **Status:** New  
* **Date Logged:** 2026-05-20  
* **Reporter:** Annalie Prinsloo  
* **Target Fix Version:** V 20260601  

### 2. Classifications
* **Defect Type:** UI / Usability
* **Severity:** Medium
* **Priority:** High
* **Reproducibility:** Intermittent (Sometimes)

### 3. Traceability & Environment
* **Traced To:** `TCOND-MM-01`, `TCOND-GP-07`
* **Hardware/Device:** Samsung Galaxy S21 FE 5G (Android 16)
* **Build Version:** Google Play Beta Build V 20260518

### 4. Description & Steps to Reproduce
* **Description:** During active gameplay and tour navigation, an error message reading "Looks like you're offline. No worries, but keep in mind some features need the internet. Want to play anytime?" erroneously displays across the bottom layout. This occurs despite a fully active, stable web connection, verified by successful concurrent third-party ad serving. It surfaced independently in two separate test executions — during the guided tour (`TC-MM-01`) and during the between-level ad transition (`TC-FLOW-03`) — indicating it is not isolated to a single screen. Severity was assessed as Medium because the app remains functional but displays misleading information; Priority was assessed as High given the chaotic sensory impact on the target ADHD user base and the fact that it affects multiple core gameplay screens.

* **Steps to Reproduce:**
  1. Open the application, go to the Game Selection area, and tap it.
  2. Apply the following options: Deck: *Colors*, Layout: *1/4*, Filter: *Shapes*, Mode: *Regular*, Backing: *Same*.
  3. Press the **Play** button.
  4. Dismiss the game information modal by tapping the "X" icon.
  5. Flip game cards to initiate active matching rounds and observe the bottom UI region.

### 5. Test Results
* **Expected Results:** The puzzle match session proceeds with zero connectivity warnings if a stable network link is present.
* **Actual Results:** A false "Looks like you're offline..." notification banner pushes onto the screen layout and remains dynamically stuck, despite live ads successfully rendering underneath.

### 6. Evidence & Attachments
* **File Attached:** `Offline-Banner-Bug-Gameplay.mp4`
* **URL:** https://youtube.com/shorts/Xaous0lJ9rs?feature=share
* **Annotation:** Clip showcases active card interactions using the "Colors" set while a persistent network error message remains stuck on screen despite live third-party ads successfully rendering.

### 7. Closure & Resolution
* **Status:** Not yet resolved (see Section 1 for current status)
* **Resolution Reason:** N/A — defect remains open pending fix
* **Closing Comment:** N/A
