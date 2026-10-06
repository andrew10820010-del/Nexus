KANDIL PACKAGING SPEC GENERATOR — INSTALLABLE APP SETUP
=========================================================

This folder turns the spec generator into an installable app (its own icon
on your laptop's desktop/Start menu/Dock, or your phone's home screen —
opens in its own window, no browser address bar).

IMPORTANT — this needs to be hosted on the web (even a free, simple host)
to become "installable". Opening index.html by double-clicking it will run
the app exactly as before, but browsers will NOT offer an "Install" button
for a file opened straight off your computer — installability requires
HTTPS. Below are two free, no-cost ways to get that in a couple of
minutes, no technical setup beyond what's described.

--------------------------------------------------------
OPTION A — Netlify Drop (fastest, no account needed)
--------------------------------------------------------
1. Go to https://app.netlify.com/drop in your browser.
2. Drag this whole folder (the one containing index.html, sw.js,
   manifest.webmanifest, icon-192.png, icon-512.png) onto the page.
3. Netlify gives you a live https:// link in a few seconds. Open it.
4. On desktop Chrome/Edge: click the install icon (a little monitor/⊕
   icon) at the right side of the address bar, or use the browser's menu
   → "Install Kandil Packaging Spec Generator..." Or just use the
   "📲 Install App" button that now appears next to Dark Mode in the app.
5. On an Android phone: open the link in Chrome, tap the ⋮ menu →
   "Add to Home screen" / "Install app" (or tap the install banner if
   Chrome shows one).
6. On an iPhone/iPad: open the link in Safari, tap the Share icon →
   "Add to Home Screen".

Note: a free Netlify Drop link is great for testing immediately, but for
a permanent company tool you'll probably want Option B or your own
server, since anonymous Netlify Drop sites can be harder to manage long
term (no login tied to it unless you create a Netlify account first).

--------------------------------------------------------
OPTION B — GitHub Pages (free, permanent, your own URL)
--------------------------------------------------------
1. Create a free GitHub account at https://github.com if you don't have
   one, then create a new repository (e.g. "kandil-specs").
2. Upload all 5 files in this folder into that repository (GitHub's web
   interface has an "Add file → Upload files" button — no command line
   needed).
3. In the repository, go to Settings → Pages, set "Source" to the main
   branch / root folder, and save.
4. GitHub gives you a URL like:
   https://<your-username>.github.io/kandil-specs/
   Wait a minute or two for it to go live, then open it.
5. Install exactly as described in steps 4–6 of Option A above.

--------------------------------------------------------
OPTION C — Your own company server / intranet
--------------------------------------------------------
If Kandil has its own web server or intranet, ask IT to drop these 5
files into a folder served over HTTPS. Same installability rules apply.
This keeps everything in-house rather than on a third-party host.

--------------------------------------------------------
WHAT STILL NEEDS INTERNET AFTER INSTALLING
--------------------------------------------------------
The app's core calculations, Packaging Manual, and KPI cards all work
fully offline once installed (and once you've opened it online at least
once). Excel / Word / PDF export use external libraries (ExcelJS, docx,
jsPDF) loaded from CDNs — the service worker caches these too, so exports
should keep working offline after that first successful load, but a
fresh install always needs one initial internet connection to fetch
everything.

--------------------------------------------------------
UPDATING THE APP LATER
--------------------------------------------------------
Whenever you get a newer version of index.html, just re-upload the files
to the same hosting location — anyone who installed the app will get the
update automatically next time they open it with an internet connection
(the service worker checks for changes and refreshes its cache).
