## Defect Report: BUG-MOB-02-04

### 1. Summary Information
* **Defect ID:** BUG-MOB-02-04  
* **Title:** Speech speed slider lacks a 100% snap-point and fine-tuning controls  
* **Status:** New  
* **Date Logged:** 2026-05-20  
* **Reporter:** Annalie Prinsloo  
* **Target Fix Version:** V 20260601  

### 2. Classifications
* **Defect Type:** UI / Usability / Accessibility
* **Severity:** Low
* **Priority:** Medium
* **Reproducibility:** Consistent

### 3. Traceability & Environment
* **Traced To:** `TCOND-CZ-01`
* **Hardware/Device:** Samsung Galaxy S21 FE 5G (Android 16)
* **Build Version:** Google Play Beta Build V 20260518

### 4. Description & Steps to Reproduce
* **Description:** The speech readback adjustment bar operates on an atypical scale spanning from 60% up to 200%. The baseline normal speed setting (100%) sits off-center within the first third of the tracking path. Because there is no default "snap-to" anchor at 100% and no incremental adjustment buttons (+/-), it is tedious for users to return to standard audio speeds. Severity was assessed as Low since a workaround exists (meticulous manual slider manipulation); Priority was assessed as Medium given that accessibility customization is a core marketing focus of the application. Note: this issue is isolated to the speech-speed control; the master volume slider (`TCOND-CZ-02`), tested in the same session, passed without incident.

* **Steps to Reproduce:**
  1. Open the **Customize** options screen.
  2. Tap and slide the narration speech speed control bar away from its default.
  3. Try to drag the slider thumb back precisely to the **100%** (Normal) position.

### 5. Test Results
* **Expected Results:** The adjustment bar should easily snap to the 100% mark, or feature side buttons to select a baseline speed directly.
* **Actual Results:** The user must meticulously pixel-hunt along an asymmetrical scale to re-engage normal playback speed, with no fine-tuning assistance.

### 6. Evidence & Attachments
* **File Attached:** `voice-speed-slider-usability.jpg`
* **Annotation:** Screenshot shows the slider thumb resting awkwardly off-center to hit 100%, highlighting the complete lack of visual notches or adjacent +/- increment controls.

### 7. Closure & Resolution
* **Status:** Not yet resolved (see Section 1 for current status)
* **Resolution Reason:** N/A — defect remains open pending fix
* **Closing Comment:** N/A
