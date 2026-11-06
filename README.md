# Pengudang website

Static site (one file: `index.html`) hosted on GitHub Pages. Uploads, replies and deletes are shared
between visitors through a free Supabase project. No server, PHP or extra apps needed.

## Setup (about 10 minutes)

### 1. Supabase (free)
1. Sign up at https://supabase.com and click **New project** (any name, any password, pick a nearby region e.g. Singapore).
2. Open **SQL Editor > New query**, paste everything from `supabase-setup.sql`, click **Run**.
3. Open **Project Settings > API**. Copy the **Project URL** and the **anon public** key.
4. In `index.html`, search for `PASTE_SUPABASE_URL_HERE` and `PASTE_SUPABASE_ANON_KEY_HERE` and paste them in.
   (The anon key is meant to be public; it is safe to commit.)

### 2. GitHub Pages
1. Create a new GitHub repository and upload `index.html` (drag and drop on the repo page works).
2. **Settings > Pages > Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`, Save.
3. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Notes
- Free Supabase projects pause after about 7 days with no activity. Open the Supabase dashboard and click Restore if that happens (or visit the site weekly).
- Free limits: 1 GB file storage, 500 MB database. Uploads are capped at 20 MB each.
- The villager passcode (`VILLAGER_CODE` in `index.html`) is checked in the browser, same as before. Anyone who
  views the page source can see it, so don't reuse a real password.
- If the two Supabase values aren't filled in, the site still works but uploads/replies only show on that device.
