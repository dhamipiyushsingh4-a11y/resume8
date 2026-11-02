# Manas College — Resume Studio

A responsive, GitHub Pages-ready resume builder with 15 templates, live preview, local multi-resume library, JSON backup/restore, job-description keyword analysis and PDF export through the browser print dialog.

## Run locally
Open `index.html` in a modern browser, or use VS Code Live Server.

## Deploy to GitHub Pages
1. Create a public GitHub repository (for example `manas-college-resume-studio`).
2. Upload `index.html`, `styles.css`, and `app.js` to the repository root.
3. Open **Settings → Pages**.
4. Under Build and deployment choose **Deploy from a branch**, select `main` and `/(root)`, then Save.
5. Open the published Pages URL.

## Included features
- 15 responsive resume layouts
- Optional profile photo upload (JPG, PNG, WebP up to 3 MB), personal profile, summary, work experience, education, skills, projects, certifications, languages, awards, volunteering and interests
- Repeatable experience/education/project/certification entries
- Live preview and browser PDF/print
- Multiple resumes, duplicate, rename via the resume selector? (Resume name is used as library label; see app.js)
- Local browser autosave
- Export/import all resumes as JSON backup
- Job description keyword overlap estimate and safe tailoring prompts

## Important: local storage vs multi-user cloud storage
This static edition saves resumes in the browser's `localStorage`. Each visitor has their own browser data. GitHub Pages does **not** provide a database, login, cross-device sync or shared user accounts.

To support many users with private accounts and cloud-synced resumes, connect a backend such as Supabase:
1. Create a Supabase project.
2. Run `supabase_schema.sql` in the Supabase SQL editor.
3. Enable Email authentication.
4. Add your Supabase project URL and **anon/public** key in a future client integration. Never put a service-role key in browser code.
5. Add row-level security (RLS) policies so users can only read/write their own rows.

The included SQL defines the secure starting schema and RLS. This version deliberately does not pretend cloud sync is active until credentials and authentication are configured.

## ATS guidance
The checker is a simple local keyword-overlap helper, not an actual ATS vendor scanner, scoring guarantee, or hiring prediction. It does not send data to a server. Review suggested keywords and only include truthful skills, qualifications and achievements.

## Privacy
Resume content is stored locally in the browser on the current device. Anyone with access to the same browser profile may be able to access it. Use Export backup before clearing browser data. Do not enter highly sensitive identity or financial information.
