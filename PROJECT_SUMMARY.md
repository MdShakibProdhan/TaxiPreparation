# Taxi Exam Study Project

A single-file interactive study tool for the Finnish taxi driver theory exam (Tampere). Built around the Arabic question doc `امتحان اسئلة التكسي.docx`, the new-folder PDF library, and image references — all bundled into one local HTML page.

## Files

- `امتحان اسئلة التكسي.docx` — original Arabic source document; correct answers marked in red.
- `For Taxi exam-20260522T212718Z-3-001/For Taxi exam/` — 12 PDF study materials plus image folders (`Book (Images)/`, `Screen shots/`).
- `taxi_exam_study_plan.html` — single self-contained study app (HTML + CSS + JS, no build step, no dependencies, ~3,400 lines).
- `PROJECT_SUMMARY.md` — this file.

## How to use

Open `taxi_exam_study_plan.html` in any browser. Everything runs locally — no server, no internet. Keep the `For Taxi exam-…/` folder next to the HTML so the PDF viewer and image galleries can find their files.

## Layout

- **Left sidebar (sticky)** holds the title and the vertical tab nav.
- **Right main area** shows the active panel.
- Responsive tiers:
  - **Desktop (>1024px)**: 240px sidebar + wide content (max 1400px).
  - **Tablet (≤1024px)**: 200px slimmer sidebar, tightened paddings.
  - **Mobile (≤768px)**: sidebar collapses into a sticky horizontal scrolling tab bar at the top.
  - **Small mobile (≤480px)**: subtitle hidden, gallery thumbnails ~85px, materials toolbar wraps.

## Tabs

### 1. 📅 20-Day Plan
A day-by-day study schedule for working through the exam material.

### 2. 🇫🇮 Vocabulary
Key Finnish vocabulary used in the exam (terms, signs, regulations).

### 3. 📚 Topics & Rules
Reference cards covering the rule areas the exam draws from.

### 4. 🧠 Quiz Me
Interactive multi-step quiz with **258 questions** total:

- 77 from the original docx (badge: **DOC**)
- 131 extracted from the new-folder PDFs (badge: **NEW DOC**, IDs 200–330) covering Kela rules, school-transport specifics, accident & first aid, driver hours / rest, Sote/VPL transports, wheelchair handling, alcohol-interlock details, vehicle inspection / licence terms, working-time / notice periods, etc.
- 50 from online sources (badge: **WEB**)

All questions use three categories that the filter buttons understand: `law`, `safety`, `service`.

**Setup screen** — choose:
- Source: **📄 Doc File Quiz** (original docx + new-folder PDFs, 208 q) or **🌐 All Questions** (doc + new + web, 258 q).
- Topic filter: All Topics / Safety / Service / Law & License / Shuffle.
- How many questions: type a number or pick a preset (5 / 10 / 20 / 50 / All).
- Click **Start Quiz**.

**Quiz screen** — answer the chosen N questions one at a time:
- Click an option to select (highlighted; no immediate feedback).
- **Previous / Next** to navigate; answers are kept when navigating back.
- On the last question, Next becomes **Submit Quiz**.
- A **Quit** button discards the run and returns to setup.

**Results screen** — full breakdown after submission:
- Big summary card with score, percentage, verdict.
- Filter list: All / Wrong only / Right only.
- For each question: question (FI + EN), your answer (red if wrong), the correct answer (green), and a short explanation.
- **New Quiz** button returns to setup.

### 5. ⚡ Quick Ref
A fast-recall training table for memorizing the question → answer pairing by their opening words.

| # | First ~3 words of question | First ~3-4 words of correct answer |
|---|---|---|

- Answers are always visible, shown in red (matching how they appear in the source doc).
- **Doc File Only / All Questions** toggle.
- **Shuffle** button to randomize order so you don't memorize positions.
- Web-sourced rows tagged with a small "W" badge.

### 6. 📖 Materials
PDF library for the 12 source documents. Sidebar lists every PDF; clicking opens it inline in the browser's native PDF viewer (zoom, scroll, search). Nothing is rewritten or summarized. "Open in new tab" link provided for full-screen reading. Documents:
- EU TaxiStars Booklet (EN) — official training booklet
- Taxi Materials (New) + answer key
- Online Material
- Side-by-Side Finnish · English
- 77 Questions, 123 Questions, 120 Questions, Questions 1–40
- Taxi Driving Material — Test 1 (34 pages)
- Kysymykset (FI)
- Emailing — Second Set

### 7. 🖼️ Book Images
Gallery of the 41 book-page photos from `Book (Images)/`. Click any thumbnail to enlarge in a lightbox. Navigate with ← → arrow keys or on-screen buttons. Esc closes.

### 8. 📸 Screenshots
Gallery of the 34 study screenshots from `Screen shots/`. Same lightbox / keyboard navigation as Book Images.

## Design

- Dark theme, monospace accents, Arabic + Latin script support.
- No frameworks. Plain HTML/CSS/JS in one file.
- Touch-friendly buttons, sticky nav on mobile.

## History of changes in this session

1. Built the original quiz limited to questions in the doc file.
2. Added a second quiz source ("All Questions") with 50 online-sourced exam questions.
3. Added the **Quick Ref** tab — first words of question and first words of correct answer side by side, for fast-recall training.
4. Removed the hover/click-to-reveal interaction in Quick Ref. Answers always show in red.
5. Added three new tabs from the `For Taxi exam-…` folder: **📖 Materials** (PDF library with sidebar + iframe viewer), **🖼️ Book Images** (lightbox gallery), **📸 Screenshots** (lightbox gallery).
6. Moved the top tab bar to a sticky **left sidebar** with the title; main content uses a wide right column.
7. Added layered responsive breakpoints for tablet (≤1024px), mobile (≤768px) and small mobile (≤480px), with the sidebar collapsing into a sticky horizontal scroller on mobile.
8. Refactored the quiz: **setup → answer all → results** flow. Added a count input (with 5/10/20/50/All presets), Previous/Next/Submit/Quit controls, and a full results screen showing each question with your answer (red if wrong) next to the correct answer (green) plus explanation. Filterable by All / Wrong / Right.
9. Extracted **131 new questions** from the new-folder PDFs (using the bilingual 77-Questions PDF with → arrows as the primary answer key) and added them as `newDocQuestions` (IDs 200–330). Pool counts: Doc 208, All 258. New questions get a **NEW DOC** badge during the quiz.
