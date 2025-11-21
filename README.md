---

# Quiz App – Teacher & Student Versions

A lightweight, fully client-side quiz system where **teachers can create quizzes** from DOCX/TXT files and **students can attempt them online** through a simple URL.

This system works entirely in the browser — **no backend required**.

---

# Features

### **Teacher Tools (QuizBuilder.html)**

* Upload **questions file** (.txt or .docx)
* Upload **answer key file** (.txt or .docx)
* Automatic parsing of:

  * Numbered questions
  * Multiple-choice options (A/B/C/D)
  * Correct answers from the key
  * Short-answer questions (no options)
* Preview full quiz before publishing
* Save quiz as a downloadable **JSON package**
* Add multiple quizzes for different subjects/units

### **Student Quiz Player (QuizPlayer.html)**

* Displays all available quizzes from `/quizzes/manifest.json`
* Students select a quiz and start immediately
* MCQs are auto-scored with correct/wrong feedback
* Short-answer questions allow students to type responses
* Clean summary showing MCQ score and detailed breakdown
* No access to raw question files → safe for students

---

# Project Structure

```
/
├── QuizBuilder.html       # Teacher-only quiz builder
├── QuizPlayer.html        # Student-facing quiz app
├── README.md
└── quizzes/
      ├── manifest.json    # List of available quizzes
      ├── python_quiz.json
      └── other quizzes…
```

---

# How to Use

## 1️⃣ Teacher: Create a quiz

1. Open **QuizBuilder.html** (locally or on a private URL)
2. Upload:

   * a **questions file** (DOCX/TXT)
   * an **answer key file** (DOCX/TXT)
3. Enter a quiz title & description
4. Review the preview panel
5. Click **Download Quiz JSON**
6. Save the JSON file in the `/quizzes` folder
7. Edit `manifest.json` to add the new quiz:

   ```json
   [
     {
       "id": "python_basics",
       "title": "Python Basics Quiz",
       "filename": "python_basics.json"
     }
   ]
   ```

---

## 2️⃣ Students: Take a quiz

Students only need to open:

```
https://<your-username>.github.io/<repo-name>/QuizPlayer.html
```

They will automatically see a list of quizzes from `/quizzes/manifest.json`.

---

# 🌐 Hosting Instructions (GitHub Pages)

1. Go to **Settings → Pages**
2. Under "Source", select:

   * Branch: **main**
   * Folder: **/root**
3. Click **Save**

Your site becomes available at:

```
https://<your-username>.github.io/<repo-name>/
```

Students access quizzes at:

```
https://<your-username>.github.io/<repo-name>/QuizPlayer.html
```

---

# Notes

* The system is 100% client-side → no servers, no databases.
* DOCX files are parsed using **Mammoth.js**.
* Short-answer questions are not auto-graded.
* Student version **does not allow uploading quiz files**.

---

# Contributing

PRs and feature requests are welcome!

Suggestions for next improvements:

* Auto-update manifest.json via builder
* Shuffle MCQs and options
* Timer/attempt limits
* Cloud-based quiz storage

---

# 📄 License

MIT License — free to use, modify, and distribute.

---
