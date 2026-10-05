## Defect Report: BUG-MOB-02-01

### 1. Summary Information
* **Defect ID:** BUG-MOB-02-01  
* **Title:** App hangs on 7th Tour screen during long load sequence  
* **Status:** New  
* **Date Logged:** 2026-05-20  
* **Reporter:** Annalie Prinsloo  
* **Target Fix Version:** V 20260601  

### 2. Classifications
* **Defect Type:** Functional / Performance (Crash/Hang)
* **Severity:** High
* **Priority:** Medium
* **Reproducibility:** Intermittent (Sometimes)

### 3. Traceability & Environment
* **Traced To:** `TCOND-MM-07`
* **Hardware/Device:** Samsung Galaxy S21 FE 5G (Android 16)
* **Build Version:** Google Play Beta Build V 20260518

### 4. Description & Steps to Reproduce
* **Description:** While connected to a stable internet connection, navigating to the 7th tour screen triggers an excessively long loading phase. During this period, the entire user interface completely freezes, causing the Exit ("X") button to become entirely unresponsive and trapping the user inside the tour view. This represents a significant risk for the target ADHD demographic due to lack of visual feedback during hangs. Severity was assessed as High given that core UI responsiveness is severely degraded and forces a hard application termination; Priority was assessed as Medium since the reduced urgency reflects the intermittent ("Sometimes") reproducibility rate observed during testing.

* **Steps to Reproduce:**
  1. Navigate to the main menu icon and tap it.
  2. Select the **Tour** option from the menu list.
  3. Tap the forward navigation arrow (right side) 6 times sequentially to reach the 7th tour screen.
  4. Attempt to tap the "X" exit button located in the tour window overlay.

### 5. Test Results
* **Expected Results:** The 7th tour screen should load quickly (< 2 seconds), and tapping the "X" button should instantly close the tour overlay and return the user safely to the main menu.
* **Actual Results:** The 7th tour screen triggers an indefinite loading loop. The main UI thread completely freezes, rendering the "X" button unresponsive and forcing a hard application termination.

### 6. Evidence & Attachments
* **File Attached:** `7th-tour-screen-ui-freeze.mp4`
* **URL:** https://youtu.be/smQAPJcSf4A
* **Annotation:** Video showcases smooth navigation through screens 1–6, followed by a total thread lock on screen 7. Multiple tap attempts on the "X" button fail completely at timestamp 6:32.

### 7. Closure & Resolution
* **Status:** Not yet resolved (see Section 1 for current status)
* **Resolution Reason:** N/A — defect remains open pending fix
* **Closing Comment:** N/A
