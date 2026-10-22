# Handoff: iamibrahimbello.xyz portfolio (as of 2026-10-22)

Ibrahim Bello's personal portfolio. One static page, `index.html` (HTML + CSS + vanilla JS, no build step),
assets in `assets/`. Git repo in this folder (branch `main`), pushed to github.com/Bello-Ibrahim1/iamibrahimbello.
**Live:** https://iamibrahimbello.xyz (also https://bello-ibrahim1.github.io/iamibrahimbello/, which redirects) (GitHub Pages, deploys from `main` / root on every push).

## Preview locally
    cd ~/Projects/iamibrahimbello && python3 -m http.server 4173    # http://localhost:4173
(In the Claude desktop app there's a launch config named "portfolio" in
`~/Desktop/ST JUDE BIOHACKATHON/.claude/launch.json` that does the same.)
`preview/hero.png` is a current screenshot of the first screen.

## What's on the page (top to bottom)
1. **Hero (light "magazine cover", Zara / The Fold-er style, combined with his earlier dark design):**
   blurred BioHackathon film looping faintly behind; handwritten-caption photos floating at the edges
   (follow the cursor); a tall centre frame; "Ibrahim Bello" wordmark; a huge headline that is black on the
   page and solid white where it crosses the frame (two text layers, clipped to the frame box with pixel
   snapping in `clipLight()`); thin uppercase links on the right; long arrows + dots flip slides.
   Slide 1 = intro ("I build with data and tell stories with a camera."), then the 6 entries in `PROJECTS`.
   Status bar chips on top (live Central-time clock). ☰ opens a full-screen menu.
2. **(01) About:** headshot, bio (Comp Sci major, Finance minor, AAMU; mission: better solutions for his
   community through collaboration, teamwork and analysis), hand-drawn squiggle/circle, "— Ibrahim"
   signature, stats (3rd PhishGuard · 2026 St. Jude Travel Award · 2nd Tracer Fire 13).
3. **(02) Projects:** PhishGuard (live screenshot of the real extension UI from the repo's
   `extension_ui_showcase.html`; links: github.com/Bello-Ibrahim1/PhishGuard, phish-guard-swart.vercel.app),
   Clinical Data Assistant (St. Jude BioHackathon AI chat: Text-to-SQL + RAG; text-only "example" cover,
   since it can't be run without credentialed MIMIC-IV data; links github.com/stjude-biohackathon/KIDS26-Team2),
   and an empty "Next project" slot.
4. **Work list:** 6 rows (BioHackathon recap, PhishGuard, NSF Spectrum Sizzle, UL Solutions (Wireless Lab
   Testing Intern), Shipt × Black Men in Tech (2025), Tracer Fire 13 & 14). Hover = preview image. PhishGuard slide holds the SecureCell photos.
5. **Map ("From Lagos to everywhere"):** d3 holographic globe, plane flies Lagos → Atlanta, then a US map
   lights GA, AL, TN, MS, NC, TX, CA, NY (`PLACES` list). d3/topojson + atlas data load from jsdelivr.
6. **Moments:** crossfading gallery with "Got a chance to meet …" captions (`MOMENTS` list): St. Jude arrival
   video, patients' art, event staff, Kerry Page (Senior VP of Data Science, St. Jude ODS), Best Overall GPT
   crew, Jewel Taylor (Director, People Business Partners, Shipt), Shipt summit, Spectrum Sizzle, UL, NY, AAMU.
7. **Contact:** ibrahim.bello.idowu@gmail.com, LinkedIn (linkedin.com/in/bello-ibrahim), Instagram @dfwbell0, GitHub.

Facts confirmed by Ibrahim: PhishGuard WAS the SecureCell hackathon project: 1st place / Best Overall ($1,500), later 3rd at AAMU STEM Day 2026; team **Zentr0**
placed 2nd at Tracer Fire 13 (Sept 2025) and 3rd at Tracer Fire 14 (Sept 13 2026, as team CyBex, $2,000; photo assets/tracerfire14.jpg, cropped to the team + check); 
NSF Spectrum Sizzle in Waco, TX (all expenses paid); Shipt + BMIT Tech Connect Emerging Talent Summit 2025.

## Resume
`assets/Bello_Ibrahim_Resume.pdf` is printed from `resume/resume.html` (one page, Letter). Rebuild:
    "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --no-pdf-header-footer --print-to-pdf=assets/Bello_Ibrahim_Resume.pdf "file://$PWD/resume/resume.html"
Check it is still 1 page. Linked from the nav, hero links, menu and Contact. Copy on his Desktop: Bello_Ibrahim_Resume_Updated.pdf.

## Changes on 2026-10-22 (later)
- Opener (slide 1 headline): "I code. I film. I build." (he rejected longer lines as too wordy).
- Status bar (.hud) is a seamless right-to-left marquee (set cloned in JS, pauses on hover), Amatic SC font
  (he picked the tall/thin "KGS" look), LOC shows 34°47′00″N 86°34′19″W, plus a left-to-right teal glow (chipglow).
- Theme follows the system (inline <head> script, no flash); the toggle saves an override, toggling back to the
  system value clears it. Light mode: warmer paper bg, white cards with soft shadows, darker teal accent2.
- Moments heading: "See the world through my lens." Footer "Built by hand" removed.
- Recap nudge (#nudge): paper card bottom-left ~6 s after first interaction, Caveat note + self-drawing spiral
  arrow to "Watch it" (opens assets/recap.mp4), dismissible, once per visit (sessionStorage).
- Map: globe flight Lagos → Washington, D.C. (Dulles), then plane hops D.C. → North Carolina → Atlanta → Alabama
  (PLACES with trip: true, in order) leaving a trail; other states light after.

- Tab title "Hi, I'm Ibrahim!"; link previews use assets/og-card.jpg (1200x630: "Hi, I'm Ibrahim!" + headshot), absolute og/twitter tags.

## His preferences for this site
- Must look creative and hand-made, **not "AI-made"**. Combine new ideas with what exists; don't replace
  sections wholesale without asking.
- Liked: Zara-style headline flip (black on page / white over photo), the blurred film, floating photos
  (keep them small), the holographic map, fading Moments.
- No low-resolution photos (Megan Hardin's photo was removed for that). No photos of himself with eyes closed.
- Always show him a preview (screenshot sent in chat + the local page) before calling something done.

## Next steps
1. ~~GitHub Pages~~ done 2026-10-22. Hero slides take an optional 3rd value per photo: `"whole"` (wide photo shown
   in full over a blurred copy, so people at the edges aren't cropped) or an object-position like `"28% 50%"`.
2. ~~Domain~~ done 2026-10-22: IONOS DNS = A @ 185.199.108-111.153, CNAME www -> bello-ibrahim1.github.io (IONOS Default Site
   records disabled; mail records left). `CNAME` file in repo. Enforce HTTPS in Settings -> Pages once the cert is issued.
   Spectrum Sizzle: he went twice, NYIT Long Island (June 2025, the AAMU article) and NSF in Waco, TX (2026). The hero slide keeps only spectrum-cert (Texas, portrait), no caption; he removed the other photos as not fitting.
   (creates `CNAME`), set the registrar DNS (A records to GitHub Pages IPs for the apex, CNAME `www` →
   bello-ibrahim1.github.io), enforce HTTPS.
3. Full recap now plays on the site: `assets/recap.mp4` (1080p, 42 MB, from final-v9-4k.mp4) via "Watch the full recap".
   When it's on YouTube, switch the first project to a YouTube embed (TODO in `PROJECTS`). Hero photos show no captions
   (he asked); captions in `PROJECTS` slides are alt text only. "Day one" was removed from Moments (it's in the hero).
4. Optional: a real (patient-data-free) screenshot of the Clinical Data Assistant; a sharper Megan Hardin photo;
   TikTok/YouTube links once he has them.
