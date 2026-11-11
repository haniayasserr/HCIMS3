# EduBot – Interactive Prototype (Milestone 2)

Clickable front-end prototype of the EduBot workflow, covering both views:

- **Student view:** Home → Upload Exam (photo/file, retake, submit) → Sent → Feedback
- **Teacher view:** Exams to review → scan + editable OCR text → AI grade confirm/change → red flags → publish

Both views share state: an exam submitted by the student appears in the teacher's list, and
feedback published by the teacher appears on the student's home screen.

## Demo flow
1. Student view: **Upload Exam** → *Take a photo* → **Submit**
2. Teacher view: open **Alex** → tap orange words to fix them → confirm Q1–Q3 → **Publish**
3. Student view: **See my feedback**

Use **Restart demo** (top right) to reset.

## Tech
Single-file HTML/CSS/vanilla JS. No build step, no dependencies (Fredoka font loaded from Google Fonts).

## Run locally
Open `index.html` in a browser, or serve it:

    python3 -m http.server 8000   # then visit http://localhost:8000

## Deploy
**GitHub Pages**
1. Create a GitHub repo and push this folder:

       git init && git add . && git commit -m "EduBot prototype"
       git branch -M main
       git remote add origin https://github.com/<your-username>/<repo>.git
       git push -u origin main

2. Repo **Settings → Pages → Deploy from a branch → main / (root)**.
3. Site goes live at `https://<your-username>.github.io/<repo>/`.

**Netlify (fastest):** drag the folder onto https://app.netlify.com/drop.

## Notes
EN | DE toggle, notifications, practice sets and Notify parent are placeholders in this prototype.
