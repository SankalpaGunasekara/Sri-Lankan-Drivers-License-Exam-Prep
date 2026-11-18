# DMT රියදුරු බලපත්‍ර ලිඛිත විභාග පුහුණුව

Free Sinhala practice site for the Sri Lanka DMT light-vehicle written exam: 171 official DMT questions, a timed 40-question paper, a wrong-question tracker, a sign library and notes.

## Put it on GitHub Pages
1. Create a new public repo on GitHub (e.g. `dmt-exam-sinhala`).
2. Upload everything in this folder to the repo root (drag and drop works). Keep `.nojekyll`.
3. In the repo, go to **Settings → Pages → Build and deployment**, set **Source: Deploy from a branch**, pick **main** and **/ (root)**, then click **Save**.
4. After about a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Turn on the suggestion box (Google Form)
1. Create a Google Form with these fields:
   - **Question** (short answer)
   - **Type** (multiple choice: Wrong answer / Unclear Sinhala / Wrong image / Suggestion)
   - **Correct answer / your message** (paragraph)
   - **Source / proof** (short answer, optional)
2. Click **Send → link** and copy the link that ends in `/viewform`.
3. Find the Question field's id: open the form's **⋮ → Get pre-filled link**, type `TEST` in Question, click **Get link**, and copy it. It contains `entry.123456789=TEST`; the `entry.123456789` part is the id.
4. Open `config.js` and fill in both values:
   ```js
   window.FEEDBACK = {
     form: "https://docs.google.com/forms/d/e/XXXX/viewform",
     questionField: "entry.123456789"
   };
   ```
5. Commit. Every question now shows a "⚑ වාර්තා කරන්න" link with the question number filled in, and the 💬 tab links to the form.
6. Read the responses in the form's **Responses** tab (or link them to a Google Sheet).

## Fixing a question
Questions and answers are in `book.js` (`n` = question number, `o` = options, `a` = correct option 1–4, `note` = explanation). Images are in `book/` (`q001.png` … `q066.png`, `d.png`).

## Files
- `index.html` – the whole app
- `book.js` – the 171 DMT questions and answers
- `config.js` – feedback form settings
- `book/` – question images and dashboard symbol pages
- `img/` – sign library images (Wikimedia Commons)

Progress and the wrong-question list are saved in each visitor's own browser (localStorage); nothing is sent to a server.

Not an official DMT site. For study only.
