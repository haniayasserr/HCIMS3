# EduBot – Interactive Prototype (HCI Milestone 2)

EduBot turns a student's photographed handwritten exam into teacher-verified, personalized feedback and AI-generated practice. This repository is a clickable front-end prototype of the **complete workflow in both the student and teacher views**, from uploading a scanned exam to viewing personalized feedback and completing personalized practice.

| | |
|---|---|
| **Repository** | https://github.com/haniayasserr/HCIMS3 |
| **Live prototype** | https://haniayasserr.github.io/HCIMS3/ |
| **Author** | Hania Yasser |

---

## 1. Quick start for the TA (2 minutes)

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

## 4. How this maps to the task analysis (HTD)

The four hierarchical task designs (`EduBot_HTD.drawio` and PNGs, submitted separately) correspond to these parts:

| HTD task | Walkthrough steps |
|---|---|
| Task 1: Student uploads an exam | Part A (1–6) |
| Task 2: Teacher verifies extracted text | Part B (7–12) |
| Task 3: Teacher reviews results, handles red flags, approves practice | Part C (13–17) |
| Task 4: Student completes a required practice set | Part D (18–23) |

---

## 5. Design decisions (Nielsen's heuristics)

| Heuristic | Where it appears |
|---|---|
| Visibility of system status | Step bar (Step 1 of 2), grade pill ("Waiting for your teacher"), "Saved just now", Approved tags, ✓ on confirmed questions |
| Match with the real world | Kid words, emoji, short text for grades 4–5 |
| User control and freedom | Back, Retake and Cancel on the upload flow; Change grade; Dismiss on flags |
| Consistency and standards | Same top bar everywhere; yellow = main action; green = correct/done |
| Error prevention | Blur reminder before Submit; Publish blocked until grades are confirmed and flags resolved |
| Recognition rather than recall | Icon + word on every button |
| Flexibility and efficiency | Take a photo or Choose a file |
| Minimalist design | One main action per screen |
| Help users recover from errors | Friendly "no worries" messages, including wrong quiz answers |
| Help | **?** button in the top bar |

---

## 6. Known limitations (prototype scope)

- All data is simulated in the browser. There is no real OCR, AI model, server or login. The sample exam page, the AI grades and feedback, and the practice questions are fixed examples written for this demo. In the real product they would be generated from each student's own work.
- The **EN | DE** toggle, the **?** help button and **Notify parent** only show a short message.
- The prototype handles a single exam page per upload.
- Practice sets and the practice quiz appear only after the teacher publishes (the same rule as the real workflow).
- The page follows the device's light or dark mode.

---

## 7. Tech and project structure

Single-file front end: HTML, CSS and vanilla JavaScript. No dependencies and no build step. The Fredoka font loads from Google Fonts (with a system fallback).

```
HCIMS3/
├── index.html   # the entire prototype
└── README.md    # this file
```

---

## 8. Deployment instructions

### Option A: GitHub Pages (used for this submission)
1. Put `index.html` and `README.md` at the root of a GitHub repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select **main** and **/ (root)**, then **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/<repo>/`. For this project: https://haniayasserr.github.io/HCIMS3/

To update the site, upload or push a new `index.html`, wait a minute, then hard-refresh (Ctrl+F5).

### Option B: Run locally
Open `index.html` in any modern browser, or serve the folder:

```
python3 -m http.server 8000
```
then visit http://localhost:8000.

### Option C: Netlify (no Git needed)
Drag the folder onto https://app.netlify.com/drop to get a live link.

### Pushing from the command line
```
git init
git add .
git commit -m "EduBot prototype"
git branch -M main
git remote add origin https://github.com/haniayasserr/HCIMS3.git
git push -u origin main
```

---

## 9. Troubleshooting

| Problem | Fix |
|---|---|
| The page is blank | Hard-refresh with Ctrl+F5. Make sure `index.html` is at the repository root. |
| The site shows a 404 | Check that Pages is set to **main / (root)** and wait a minute or two after saving. |
| No personalized feedback or practice | The teacher must publish first: confirm Q1–Q3, resolve any red flags, then tap **Publish feedback to student**. |
| Something looks stuck | Tap **Restart demo** to reset. |
