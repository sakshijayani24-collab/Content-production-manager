# Content Production Manager

A shared toolkit for the content production team — Python scripts for downloading, trimming, and searching video content, plus Claude skill files for AI-assisted writing tasks.

Clone this repo and you'll know what's here and how to use it in under five minutes.

---

## What's in Here

| Folder | What it contains |
|--------|-----------------|
| `scripts/` | Python scripts for video downloading, clip cutting, and transcript search |
| `skills/` | Claude skill files (.md) that guide AI behavior for writing tasks |

---

## Scripts (`/scripts`)

### script1.py — Video Downloader

**What it does:** Downloads videos from a YouTube playlist or channel URL using yt-dlp. Saves each video as an .mp4 with the upload date and title in the filename.

**Input:** A YouTube playlist or channel URL

**Output:** .mp4 files saved to an output folder (default: `./downloads`)

**Dependencies:** Install yt-dlp first: `pip install yt-dlp`

**How to run:**

`python scripts/script1.py "https://www.youtube.com/playlist?list=YOUR_PLAYLIST"`

**Optional flags:**

| Flag | What it does | Default |
|------|-------------|---------|
| `--out` | Folder to save videos into | `./downloads` |
| `--max` | Max number of videos to download | All of them |
| `--quality` | Max video height in pixels (e.g. 720, 1080) | `720` |

---

### clip_batch.py — Batch Clip Cutter

**What it does:** Reads a CSV file of timestamps and cuts multiple clips from video files in one go using ffmpeg. Each clip is saved as its own .mp4.

**Input:** A CSV file with columns: `source_file`, `start`, `end`, `label` — plus a folder of source videos. Times can be in seconds or HH:MM:SS format.

**Output:** Individual .mp4 clip files saved to your chosen output folder

**Dependencies:** Install ffmpeg first: `brew install ffmpeg`

**How to run:**

`python scripts/clip_batch.py clips.csv ./source_videos ./output_clips`

---

### TRANSCRIPT_TOOL_v2.py — Transcript Phrase Finder

**What it does:** Searches a Whisper-generated transcript JSON file for a phrase and returns every timestamp where that phrase appears, with surrounding text.

**Input:** A Whisper transcript `.json` file and a search phrase

**Output:** Printed list of timecodes and matching text lines

**Dependencies:** None — uses Python standard library only

**How to run:**

`python scripts/TRANSCRIPT_TOOL_v2.py transcript.json "your search phrase"`

---

## Skills (`/skills`)

Claude skill files tell the AI when and how to apply specialized behavior. Load these into Claude when working on the task they describe.

| File | When to use it |
|------|---------------|
| `skills/memo_skill_v3.md` | Writing or editing internal memos |
| `skills/POLL_SKILL.md` | Creating audience polls or survey questions |
| `skills/radio ad skill.md` | Writing radio advertisement scripts |

---

## Setup and Dependencies

| Tool | Required by | How to install |
|------|------------|----------------|
| Python 3.8+ | All scripts | https://www.python.org/downloads/ |
| yt-dlp | script1.py | `pip install yt-dlp` |
| ffmpeg | clip_batch.py | `brew install ffmpeg` |
| Nothing extra | TRANSCRIPT_TOOL_v2.py | No install needed |

---

## How to Add Something New

**Adding a new script:**
1. Put it in the `scripts/` folder
2. Name it using lowercase and underscores: `what_it_does.py`
3. Add a section for it in this README under Scripts

**Adding a new skill:**
1. Put it in the `skills/` folder
2. Name it: `skill_name.md`
3. Add a row for it in the Skills table above

---

## Cloning This Repo

`git clone https://github.com/sakshijayani24-collab/content-production-manager.git`
