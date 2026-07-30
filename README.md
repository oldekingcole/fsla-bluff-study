# Bluff Vegetation Survey — client site

A ready-to-publish website for the bluff vegetation survey. Hosts on GitHub Pages with **no command
line and nothing to install** — everything uploads through github.com in the browser.

`index.html` is tiny (20 KB); the media are separate files so each one stays well under GitHub's
**25 MB per-file** browser-upload limit. Every deliverable has a **Download** and a **View** on the page.

## Publish it (browser only)

1. github.com → sign in → **New repository** → name it (e.g. `bluff-survey`), **Public**, Create.
2. **Add file → Upload files.** GitHub caps how much you can upload in **one** commit, so upload in a
   few small batches instead of all at once (that was the earlier "file too large" error):
   - **Batch A** (drag these together, ~12 MB): `index.html`, `.nojekyll`, `README.md`, `REPORT.md`,
     the three `veg_areas_*.csv`, `facade.jpg`, `facade_veg.png`, `topdown_overlay.png`,
     `bluff_3d_flythrough.mp4` → **Commit**.
   - **Batch B:** `veg_polygons.geojson` (10 MB) → Commit.
   - **Batch C:** `bluff_splat_web.ply` (19 MB) → Commit.
   - **Batch D:** `bluff_mesh_web.ply` (18 MB) → Commit.
   (Turn on "show hidden files" so you can see `.nojekyll`.)
3. **Settings → Pages** → Source = **Deploy from a branch**, Branch = **main** / **/ (root)** → Save.
4. Live in ~1 min at **https://<username>.github.io/<repo>/** — that's the link to share.

## What works once it's live
- **Interactive façade** (pan/zoom + vegetation toggle + zones), **satellite map** of the top-down ortho,
  the **3D flythrough** video, and the numbers — all in the browser.
- **Open the Gaussian splat** → SuperSplat, **Open the 3D mesh** → Online3DViewer. These build their links
  from the site's own address and GitHub Pages serves the `.ply` files with the right CORS header, so they
  open the live 3D with nothing to install. (They work on the published site, not on a local double-click.)
- Every deliverable also has a **Download** button.

## Full-resolution files (delivered separately)
The full façade ortho (326 MB), top-down GeoTIFF (555 MB), full splat (81 MB) and full mesh (127 MB)
exceed browser-upload limits — delivered in the project folder / share link. To put any on the site,
add it as a **Release** asset (Releases → Draft a new release → drag the file; up to 2 GB, also CORS-served).

## Prefer one upload instead of batches?
Install **GitHub Desktop** (a GUI app, no command line): drag this folder into a new repo and click
Publish — it pushes everything at once (and can handle the full-res files too, up to 100 MB each).
