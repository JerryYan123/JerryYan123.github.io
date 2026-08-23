# jerryyan123.github.io

Personal academic website, built on [al-folio](https://github.com/alshedivat/al-folio).

## Deploy (one time)

1. Create a GitHub repo named exactly **`JerryYan123.github.io`** (must match your username, or the
   site will not be served at the root domain).
2. From this folder:

   ```bash
   git init
   git add -A
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/JerryYan123/JerryYan123.github.io.git
   git push -u origin main
   ```

3. **Settings → Actions → General → Workflow permissions → "Read and write permissions"**, then Save.
   Without this the build succeeds but the deploy step cannot push, and nothing appears.
4. Push (or re-run the action). The `Deploy site` workflow builds the site and force-pushes the
   result to a **`gh-pages`** branch. First run takes ~3 minutes.
5. **Settings → Pages → Build and deployment → Source = "Deploy from a branch"**, branch **`gh-pages`**,
   folder **`/ (root)`**. Save.

   > Not "GitHub Actions" as the source — this workflow uses the branch-push method, so picking
   > GitHub Actions there would serve nothing.

The site then lives at <https://JerryYan123.github.io>.

You do **not** need Ruby or Jekyll installed — GitHub Actions builds it. (Local preview would need
Ruby 3.x + `bundle install`; the system Ruby 2.6 on macOS is too old.)

## Where to edit what

| What | File |
|---|---|
| Bio, profile photo caption | `_pages/about.md` |
| News items on the front page | `_news/announcement_*.md` (one file each) |
| Publications | `_bibliography/papers.bib` |
| CV content | `_data/cv.yml` |
| CV PDF download button | `assets/pdf/Jerry-CMUCS-CV.pdf` |
| Email, GitHub, LinkedIn, Scholar | `_data/socials.yml` |
| Site title, URL, description | `_config.yml` |
| Co-author name → homepage links | `_data/coauthors.yml` |

## Still to do

- [ ] Replace `assets/img/prof_pic.jpg` with your own photo (square crop works best).
- [ ] Fill in `scholar_userid` in `_data/socials.yml` once you have a Google Scholar profile
      (it is the string after `user=` in your profile URL). Leave blank to hide the icon.
- [ ] Add the arXiv link to the agentic-systems paper in `_bibliography/papers.bib`
      (`arxiv = {2601.xxxxx}`).
- [ ] Two papers are commented out at the bottom of `papers.bib` — uncomment each as it goes public.

## Notes

`baseurl` in `_config.yml` is intentionally **blank**. That is correct for a `USERNAME.github.io`
root site; the al-folio template repo itself uses `/al-folio` because it is served from a subpath.
