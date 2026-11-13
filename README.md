# EduBot – Interactive Prototype (HCI Milestone 3)

EduBot turns a student's photographed handwritten exam into teacher-verified, personalized feedback and AI-generated practice. This repository is a clickable front-end prototype of the **complete workflow in both the student and teacher views**, from uploading a scanned exam to viewing personalized feedback and completing personalized practice.

| | |
|---|---|
| **Repository** | https://github.com/haniayasserr/HCIMS3 |
| **Live prototype** | https://haniayasserr.github.io/HCIMS3/ |
| **Author** | Hania Yasser |

---

## 1. Quick start 

1. Open the live prototype: https://haniayasserr.github.io/HCIMS3/ (or open `index.html` locally).
2. Follow the full walkthrough in section 3. Both views share state, so an exam submitted by the student appears in the teacher's list, and feedback published by the teacher appears on the student's home screen.
3. Use **Restart demo** (top right) at any time to reset the prototype to its starting state.

No installation, login or build step is needed. Everything runs in the browser.

---

## 2. What is in the prototype

### Student view (designed for grades 4–5)
| Screen | What it shows |
|---|---|
| **Home** | Welcome card, big yellow **Upload Exam** button, **Latest grade** card with status, progress chart, practice sets, badges |
| **Upload Exam** (Step 1 of 2) | **Take a photo** / **Choose a file**, exam preview, blur hint, **Retake**, **Submit**, **Cancel** |
| **Sent!** (Step 2 of 2) | Confirmation that the exam reached the teacher, **Back home** |
| **My feedback** | Total score, stars, a short kid-friendly comment per question |
| **My practice** ("Made for you") | The three AI-generated practice sets, each with the reason it was created |
| **Practice quiz** | 3 questions per set, instant friendly feedback, score and badge message at the end |

### Teacher view
| Screen | What it shows |
|---|---|
| **Exams to review** | Inbox with status tags (Needs review / Published) |
| **Verification screen** | Student and exam header, Q1–Q3 tabs, scanned answer with detected boxes (left), editable extracted text with low-confidence words (right), AI grade and feedback with confidence, red flags, AI practice sets panel, **Publish feedback to student** |

### Unique feature: AI-generated personalized practice
After the teacher verifies the exam, EduBot builds practice sets from the student's own feedback: chlorophyll (from Question 2), oxygen in cells (from Question 1) and spelling of science words (from the flagged words in Questions 1 and 3). The teacher sees these in an **"AI practice sets"** panel and approves them by publishing, so nothing reaches the student unchecked. The student then sees them on the home screen and in **Practice next**.

---

## 3. Full walkthrough (follow these steps in order)

### Part A: Student uploads an exam
1. Open the prototype. You are in **Student view** on the Home screen.
2. Tap **Upload Exam**.
3. Tap **Take a photo** (or **Choose a file**). A preview of a sample exam page appears.
4. *(Optional)* Tap **Retake** to clear the preview and add it again. Tap **Submit** with no picture to see the friendly "no worries" message.
5. Tap **Submit**. The **Sent!** screen (Step 2 of 2) confirms the upload.
6. Tap **Back home**. The Latest grade card now says **Waiting for your teacher**.

### Part B: Teacher verifies the extracted text
7. Tap **Teacher view** (top left toggle).
8. In **Exams to review**, open **Alex** (the exam just submitted). Anna Müller is a pre-loaded example you can also open.
9. Check the identity fields at the top (student name, exam title and form).
10. In the split view, compare the scanned answer (left) with the extracted text (right). The scan line marked "low confidence" has an orange outline.
11. Tap each orange word in the extracted text to fix it. The word turns green and the orange scan box disappears.
12. Tap **Q2** and **Q3** to check the other questions. Tap **Q1** to return.

### Part C: Teacher reviews results and approves
13. For each question (Q1, Q2, Q3), read the AI grade (out of 10), confidence and feedback, then tap **Confirm grade**. A ✓ appears on the question tab.
14. *(Optional)* Tap **Change grade**, use **−** / **+**, then **Save**. The total score on the student's side updates accordingly.
15. Check **Red flags**. Alex has none. *(To try red flags, open Anna Müller instead: use **Confirm flag** or **Dismiss** on each flag, and **Notify parent** after confirming a flag.)*
16. Read the **AI practice sets** panel (made from this feedback).
17. Tap **Publish feedback to student**. Publishing needs all 3 grades confirmed and all red flags resolved; otherwise a message explains what is missing.

### Part D: Student sees feedback and completes practice
18. Tap **Student view**.
19. The Latest grade card now shows the score (24/30 with the default grades) and a **See my feedback** button. Tap it.
20. Read the total score, stars and the comment for each question.
21. Tap **Practice next** (or tap a set in the Practice sets list on the home screen).
22. Open a set (for example **Chlorophyll and green leaves**). Answer the 3 questions: tap an option, read the instant feedback (green = right, "No worries! The answer is…" = wrong), then tap **Next** or **Finish**.
23. See your score and badge message. Tap **More practice** to try another set or **Back home**.



---

## Run the code on your laptop



### Option 1: Download and double-click (easiest)

1. Open the repository: https://github.com/haniayasserr/HCIMS3
2. Click the green **Code** button, then **Download ZIP**.
3. Unzip the file. On Windows, right-click it and choose **Extract All**.
4. Open the unzipped folder `HCIMS3-main` and double-click `index.html`. It opens in your browser and the prototype runs.

### Option 2: Clone with Git

1. Open a terminal (Command Prompt, PowerShell or Terminal).
2. Run:

   ```
   git clone https://github.com/haniayasserr/HCIMS3.git
   cd HCIMS3
   ```

3. Open `index.html`:
   - Windows: `start index.html`
   - Mac: `open index.html`
   - Linux: `xdg-open index.html`

### Option 3: Run it as a local web server

From inside the project folder, run one of these:

- **Python:** `python -m http.server 8000` (on Mac/Linux: `python3 -m http.server 8000`)
- **VS Code:** install the "Live Server" extension, right-click `index.html`, then choose **Open with Live Server**

Then visit http://localhost:8000 in your browser. Press Ctrl+C in the terminal to stop the server.

### Option 4: No download at all

Open the live version: https://haniayasserr.github.io/HCIMS3/
|---|---|
| The page is blank | Hard-refresh with Ctrl+F5. Make sure `index.html` is at the repository root. |
| The site shows a 404 | Check that Pages is set to **main / (root)** and wait a minute or two after saving. |
| No personalized feedback or practice | The teacher must publish first: confirm Q1–Q3, resolve any red flags, then tap **Publish feedback to student**. |
| Something looks stuck | Tap **Restart demo** to reset. |
