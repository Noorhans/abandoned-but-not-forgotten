# Abandoned but Not Forgotten
**NASA Space Apps Challenge: Storytelling about NASA's Discarded Equipment on the Moon and Mars**

An interactive web app that introduces school-age space fans to 22 pieces of NASA hardware left on the Moon and Mars. Each object tells its own story in the first person, explains the science it made possible, and ends with a quiz that earns a badge.

## Features
- 🌐 **English and Kurdish (Sorani)**: full interface and all stories, quizzes and facts in both languages, with right-to-left layout for Kurdish (button in the header; open with `#ku` or `#mars-ku` to start in Kurdish)
- 🌕 / 🔴 **Moon and Mars maps** made from real NASA Solar System Treks tiles, with every object at its real coordinates
- 💬 **First-person stories**: "Hi, I'm Opportunity…"
- 🔊 **Narration** through the browser's built-in speech
- ⏱️ **Planned vs. real life bars**, e.g. Opportunity lasted about 57 times longer than planned
- 📅 **Timeline slider and "play history"**, so hardware appears on the map year by year (1964 → today)
- ▶ **Guided story tour** in date order, Moon first and then Mars
- 🧠 **Quizzes and badges** with ranks from Cadet to Space Historian, saved in the browser
- 📸 **Live NASA photos** for each object from the NASA Image and Video Library API
- 📚 **Sources** for every object: NSSDCA catalog entry, LROC / HiRISE orbital views, images.nasa.gov

## NASA open data used
| What | Source |
|---|---|
| Moon basemap | Solar System Treks WMTS – LRO WAC Global Mosaic (`trek.nasa.gov/tiles/Moon/EQ/LRO_WAC_Mosaic_Global_303ppd_v02`) |
| Mars basemap | Solar System Treks WMTS – Viking MDIM 2.1 Color Mosaic (`trek.nasa.gov/tiles/Mars/EQ/Viking_MDIM21_ClrMosaic_global_232m`) |
| Photos | NASA Image and Video Library API (`images-api.nasa.gov/search`) |
| Mission facts | NSSDCA Master Catalog (`nssdc.gsfc.nasa.gov`) and NASA mission pages |
| Orbital "then & now" | LROC (lroc.asu.edu), HiRISE (uahirise.org) |

If the live map tiles can't load (offline, or a sandboxed preview), the app draws an offline illustration with the same real coordinates and region names.

## Run it
Everything is in one file. Open `index.html` in a browser.

**Publish on GitHub Pages (free):**
1. Create a new public repo and upload `index.html`, `README.md` and the `data/` folder.
2. Go to **Settings → Pages**, set Source to **Deploy from a branch**, choose branch `main` and folder `/ (root)`.
3. Your site goes live at `https://<username>.github.io/<repo>/`.

## Editing content
The hardware data lives in two places:
- `data/hardware-data.js` (English) and `data/hardware-data-ku.js` (Kurdish) are readable copies for editing and review.
- `index.html` has the same data inlined near the bottom. Search for `const HARDWARE`.

After you edit, paste the updated `HARDWARE` array back into `index.html`. Each object has:
`id, world, name, mission, type, icon, year, end, lat, lon, place, status, story, science, fun, query, nssdc, quiz{q, options, answer, explain}`, plus optional `plannedDays / actualDays / unit`.

## Before you submit (checklist)
- [ ] Check dates, numbers and coordinates against the NSSDCA catalog and NASA mission pages
- [ ] Open each NSSDCA link to confirm it shows the right spacecraft
- [ ] Test live map tiles and photos after deploying to GitHub Pages
- [ ] Record a 30-second demo: choose a world, play the timeline, open Opportunity, take the quiz
- [ ] Have a native speaker proofread the Kurdish text
- [ ] Ideas to add: Arabic translation, side-by-side LROC "then & now" photos, more objects (Surveyor 5/6/7, ALSEP stations, Mars heat shields)

Image credits: NASA (public domain). LROC images: NASA/GSFC/Arizona State University. HiRISE images: NASA/JPL-Caltech/University of Arizona.

## Use of AI

This project was built with the help of Claude (Anthropic), an AI assistant (large language model). Claude helped write the app's code (HTML, CSS and JavaScript, including the map, timeline, quiz and language-switching logic), drafted the English stories, facts and quizzes, translated them into Kurdish (Sorani), and helped design the presentation slides.

Our team chose the challenge, the concept and the audience, selected which NASA hardware to feature, reviewed the facts against NASA sources, proofread the Kurdish, and tested and presented the app.

No AI-generated photos, video or audio are used. All photos come from the NASA Image and Video Library. The small decorative graphics (the app logo and the offline fallback map) are simple shapes drawn by AI-assisted code.

Team: Noorhan Salah, Vare Latif, Vana Salam, Solin Sirwan, Elyan Bashir.
