Civil Engineering Visual Library
A two-image teaching tool for civil engineering onboarding. Every slide pairs a real-world view with a CAD view (or before/after, plan/section, etc.) and supports voice narration so trainers can talk viewers through what they're seeing.
Live site: https://ssloop25.github.io/Civil-Engineering-Visual-Library/

What's in this repo
.
├── index.html          # The public viewer (what visitors see)
├── editor.html         # The private authoring tool (do not share)
├── data/
│   └── library.json    # All slide content (titles, labels, lessons, narration paths)
├── media/
│   ├── images/         # Slide images (committed to repo)
│   └── audio/          # Voice narrations (committed to repo)
└── README.md

How to publish updates (the simple way)

Open editor.html locally by double-clicking it. (It runs entirely in your browser — no server needed.)
Add slides, upload images, record voice narration, fill in teaching notes. Everything autosaves to your browser as you go.
When you're ready to publish, click the Publish button at the top right.
The editor builds a zip file and downloads it to your computer.
Unzip the file into this repo folder, replacing the existing data/ and media/ folders.
Open Terminal (or GitHub Desktop) in this folder and run:

   git add .
   git commit -m "Update library"
   git push

Wait ~1 minute. Your site at the URL above is now updated.


First-time setup (one-time)
1. Clone the repo to your computer
If you've already done this, skip. Otherwise:
git clone https://github.com/ssloop25/Civil-Engineering-Visual-Library.git
cd Civil-Engineering-Visual-Library
2. Turn on GitHub Pages

Go to your repo settings.
Under Source, choose Deploy from a branch.
Under Branch, choose main and / (root).
Click Save.
After ~1 minute, GitHub will show your live URL — it should be:
https://ssloop25.github.io/Civil-Engineering-Visual-Library/

3. Push the initial files
If this repo is empty, copy everything from this folder into it and run:
git add .
git commit -m "Initial library"
git push

Using the editor
Adding images

Click any image slot to upload a photo or CAD export.
You can also drag a file directly onto the slot.
Use the Image A type and Image B type dropdowns in the Teach tab to label what kind of view each is (Real-world photo, CAD plan view, Cross-section, etc.).

Recording narration

Open the Voice tab on the right.
Hit Record — your browser will ask for microphone permission once.
Walk through the 5-question script (visible right below):

What is image A?
What is image B?
What should they notice?
Why does it matter?
Takeaway


Click Stop when done. The recording is saved with the slide.
You can also upload an existing audio file (.mp3, .wav, .m4a).

Filling in teaching content
The Teach tab has 5 textareas matching the question scaffold. Fill these in to make the slide self-explanatory even without voice — the public viewer surfaces them on each slide.
Organizing slides

Use the up/down arrows in the canvas toolbar to reorder slides.
Use the duplicate icon to copy a slide as a starting point for a similar one.
Add a new module via + ADD in the sidebar.

Backups
The Backup button in the top bar exports a JSON file of your entire library. Keep these as safety copies — useful if your browser cache gets cleared before you publish.

Where files end up after Publish
When you Publish, the bundle reorganizes everything for git:

Images become files in media/images/ named like <slide-id>-A.jpg, <slide-id>-B.jpg.
Audio becomes files in media/audio/ named like <slide-id>.webm.
data/library.json is rewritten to reference those files by path (no more giant base64 strings).

This keeps your git repo clean, diff-friendly, and small enough to grow over time.

Tips for a healthy repo

Image size: resize images to ~1600px wide before uploading. A 4MB phone photo bloats the repo for no visual gain.
Audio length: keep narrations under 90 seconds per slide. Voice files compound fast.
Commit early, commit often: don't let edits pile up locally for weeks before pushing.
Don't share editor.html: it includes a noindex tag so search engines won't list it, but the URL is technically reachable. Treat it like a draft tool.


Troubleshooting
My changes aren't showing on the live site

GitHub Pages usually publishes within a minute. Check the Actions tab of your repo for a green checkmark.
Force-refresh the public URL with Cmd/Ctrl + Shift + R to bypass the browser cache.

The editor says "Storage full"

Browser localStorage caps around 5–10 MB. Big audio files fill it quickly.
Hit Publish to flush content into the bundle, then delete the slide images locally to free space, OR just publish more often.

The Publish bundle is huge

Compress your images before uploading (try tinypng.com).
Trim long narrations.

Pages says "404"

Make sure your repo's index.html is at the root (not in a subfolder).
Confirm GitHub Pages is enabled on the main branch from / (root) in repo settings.


License
Internal training material for Rodgers Consulting.
Creating communities with clients who share our values.
