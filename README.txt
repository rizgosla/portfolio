RIZ GOSLA — PORTFOLIO SITE
==========================

This folder contains everything for rizgosla.com. No build tools, no
frameworks. Just HTML and CSS you can open in any text editor.


FILE STRUCTURE
--------------

  index.html              ← the homepage
  changelog.html          ← version log / "what's new" page
  styles.css              ← all the styling for every page
  README.txt              ← this file
  projects/
    _template.html        ← duplicate this to create new project pages
    example-project.html  ← example of a filled-in project page


HOW TO ADD A NEW PROJECT
------------------------

1. Open the `projects` folder.

2. Make a copy of `_template.html`. Rename the copy to something short
   and URL-friendly — lowercase, words separated by dashes. For example:
       cycloidal-drive.html
       knee-rehab-device.html
       wave-optics-sim.html

3. Open your new file in a text editor (Notepad, TextEdit, VS Code —
   anything works). Find and replace every [bracketed placeholder]
   with real content. Also update the <title> tag near the top of the
   file.

4. Open `index.html` and find the Projects section. Duplicate one of
   the existing `<a class="project">` blocks and update:
       - the `href` to point at your new file
         (e.g. href="projects/cycloidal-drive.html")
       - the year, title, description, and tags

5. Save both files. Re-upload to your host (Netlify, etc.).

   That's it.


HOW TO ADD A CHANGELOG ENTRY
----------------------------

1. Open `changelog.html`.

2. Find the first `<div class="changelog-entry">` block. Copy it and
   paste a new copy ABOVE it (newest entries go at the top).

3. Update the version number, date, title, and bullet points in your
   new copy.

4. Save. Re-upload.


HOW TO ADD A BRAND NEW TOP-LEVEL PAGE
-------------------------------------

Say you want to add a "Writing" or "Blog" page.

1. Copy `changelog.html` and rename it (e.g. `writing.html`).
2. Replace the page contents with whatever you want.
3. Open EVERY html file in the site (index.html, changelog.html, and
   every file inside /projects) and add a new <li> to the nav <ul>:

       <li><a href="writing.html">Writing</a></li>

   For files inside /projects, remember to use `../writing.html`
   instead of just `writing.html`.

   This is the one annoying part of a no-build site: adding a nav link
   means editing every file. With ~5–10 files it's a 2-minute job.


HOW TO CHANGE THE DESIGN
------------------------

All colors, fonts, and spacing live in `styles.css`. The most-edited
section is at the very top:

    :root {
      --bg: #0b0b0c;         ← page background
      --ink: #f5f5f2;        ← main text color
      --accent: #c6ff4a;     ← lime green accent (links, highlights)
      ...
    }

Change these values and every page updates at once. No need to touch
the HTML files.


HOW TO ADD IMAGES TO A PROJECT PAGE
-----------------------------------

1. Make a folder called `images` inside `projects/`.
2. Put your image file there (jpg, png, or webp).
3. In your project HTML file, add this line where you want the image:

       <img src="images/my-diagram.png" alt="Short description">


HOW TO ADD YOUR RESUME
----------------------

1. Export your resume as a PDF.
2. Name the file `resume.pdf`.
3. Drop it in this folder (the same folder as index.html).
4. The download button on the site will pick it up automatically.
   (If you don't have a resume section yet, add one — see how the
    existing sections are built for the pattern.)


DEPLOYING TO NETLIFY
--------------------

1. Go to netlify.com and sign up (free).
2. On the dashboard, find the "deploys" area and drag this ENTIRE
   folder onto the drop zone (not just one file — the whole folder,
   so the paths work).
3. Netlify gives you a random URL like `brave-leaf-1234.netlify.app`.
   Your site is live.
4. To connect rizgosla.com: in Netlify go to Domain Settings → Add
   Custom Domain → enter rizgosla.com. Netlify will show you DNS
   records to add in GoDaddy's DNS Management panel. Add them, wait
   10–30 minutes, done.


WHEN YOU MAKE UPDATES
---------------------

Every time you edit files and want them live:
- Drag the folder onto Netlify again (it replaces the old version), OR
- Set up GitHub + Netlify auto-deploy (more setup up front, but then
  every GitHub commit auto-deploys). Worth it once you're editing often.
