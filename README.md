# SimpCity Grabber — one-click scene grabbing straight to your seedbox

Turn any SimpCity thread into a grab-and-go library builder. This script reads a post, works out the exact
scene, searches **your** trackers through Prowlarr, and fires the release at your download client — with
posters, a live download manager, grab history, and duplicate detection built in. No file-hosts, no manual
searching, no copy-pasting release names.

> ⚠️ **This is not a plug-and-play toy for newbies.** It drives *your* infrastructure. If you don't already
> run an indexer manager and have tracker access, this isn't for you (yet). Read the Requirements before you buy.

---

## What it does
- Adds a **Torrent** button to every post — click it and it resolves the scene, searches your trackers, and shows you the matches to pick from (with posters + studio logos pulled from Stash).
- **Smart, format-agnostic scanning** — reads studio + date + title out of almost any post layout, megapack contents lists included.
- **Live download manager** — progress, pause/resume/delete, category filter, and sort, right on the page.
- **Grab history + duplicate alerts** — remembers everything you've grabbed (with posters) and warns you if a scene is already in your history or already in qBittorrent.
- **Freeleech-first mode** — prefer or restrict to freeleech releases to protect your ratio.
- **Straight + lesbian filter** — drops trans/gay results by default (toggle in Settings).

## Requirements (read this)
You supply the backend. The script is the remote control; **you** own the machine.
- **Prowlarr** (required) — reachable from your browser, with your trackers added. This is what actually searches.
- **A download box** — a seedbox or your own server running **qBittorrent** (WebUI enabled). Grabs land there, not on your PC.
- **Tracker access** — you need accounts on the trackers Prowlarr searches. The script finds nothing your trackers don't have.
- **Optional but recommended:** **Stash** (StashDB API) for posters + accurate scene dates; **Whisparr/Radarr** if you want library automation.
- **Tampermonkey** in a Chromium browser or Firefox.

If those words are unfamiliar, this tool won't help you — it's for people who already run this kind of setup.

## Install
1. Install **Tampermonkey**.
2. Install the grabber from the link you were given, then **activate** it with your license key (one key = one device).
3. Open any SimpCity thread — the first time, a **Settings** panel opens automatically.

## Configure (Settings panel)
Open it from the **gear** in the download manager, or the Tampermonkey menu → **"Grabber settings."**
- **Prowlarr** — your URL (e.g. `http://192.168.1.x:9696`) + API key (*Prowlarr → Settings → General*). Hit **Test**.
- **Stash** *(optional)* — enable it, GraphQL URL + API key. **Test.**
- **qBittorrent** *(optional)* — enable the manager, WebUI URL + user/pass. **Test.**
- **Filtering** — freeleech preference, min seeders, categories, content filter.
- **Save & reload.**

Your keys live **locally in Tampermonkey** — nothing is sent anywhere except to the servers *you* configure.

## Tampermonkey settings to check
- **Allow cross-origin requests:** the first time it talks to your Prowlarr/qBit, Tampermonkey pops a "cross-origin resource" prompt — click **Always allow** for your own hosts. That's expected (the script can't know your addresses in advance).
- **Auto-updates:** in the Tampermonkey dashboard, set **Check for updates** to *Every day* so you get new versions automatically.
- **Make sure it's enabled** on the SimpCity domains (it matches `simpcity.cr / .su / .is / .cz / .hk / .rs / .ax`).

## Using it
- **One post:** click **Torrent** → pick a release → it's sent to your box. The button shows a little number = scenes detected in that post.
- **Download manager:** the pill bottom-right shows live progress; filter by category, sort, pause/resume/delete.
- **History:** the clock icon (or TM menu) — everything you've grabbed, with posters.
- **Duplicates:** the picker flags scenes you already grabbed or already have in qBittorrent.

## Notes
- **Privacy:** keys stored locally; the script only contacts your own services + the license check.
- **Device-locked:** one license = one device. New machine? You can move it — just ask.
- **It finds what your trackers have.** Empty results usually means the release isn't on your trackers, not a bug.

## Support
Questions, a device move, or a bug — reach out where you got your key.
