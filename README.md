Content Production Manager
A shared toolkit for the content production team — Python scripts for downloading, trimming, and searching video content, plus Claude skill files for AI-assisted writing tasks.
Clone this repo and you'll know what's here and how to use it in under five minutes.

What's in Here
FolderWhat it containsscripts/Python scripts for video downloading, clip cutting, and transcript searchskills/Claude skill files (.md) that guide AI behavior for writing tasks

Scripts (/scripts)
script1.py — Video Downloader
What it does: Downloads videos from a YouTube playlist or channel URL using yt-dlp. Saves each video as an .mp4 with the upload date and title in the filename.
Input: A YouTube playlist or channel URL
Output: .mp4 files saved to an output folder (default: ./downloads)
Dependencies: Install yt-dlp first: pip install yt-dlp
How to run:
python scripts/script1.py "https://www.youtube.com/playlist?list=YOUR_PLAYLIST"
Optional flags:
FlagWhat it doesDefault--outFolder to save videos into./downloads--maxMax number of videos to downloadAll of them--qualityMax video height in pixels (e.g. 720, 1080)720

clip_batch.py — Batch Clip Cutter
What it does: Reads a CSV file of timestamps and cuts multiple clips from video files in one go using ffmpeg. Each clip is saved as its own .mp4.
Input: A CSV file with columns: source_file, start, end, label — plus a folder of source videos. Times can be in seconds or HH:MM:SS format.
Output: Individual .mp4 clip files saved to your chosen output folder
Dependencies: Install ffmpeg first: brew install ffmpeg
How to run:
python scripts/clip_batch.py clips.csv ./source_videos ./output_clips

TRANSCRIPT_TOOL_v2.py — Transcript Phrase Finder
What it does: Searches a Whisper-generated transcript JSON file for a phrase and returns every timestamp where that phrase appears, with surrounding text.
Input: A Whisper transcript .json file and a search phrase
Output: Printed list of timecodes and matching text lines
Dependencies: None — uses Python standard library only
How to run:
python scripts/TRANSCRIPT_TOOL_v2.py transcript.json "your search phrase"

Skills (/skills)
Claude skill files tell the AI when and how to apply specialized behavior. Load these into Claude when working on the task they describe.
FileWhen to use itskills/memo_skill_v3.mdWriting or editing internal memosskills/POLL_SKILL.mdCreating audience polls or survey questionsskills/radio ad skill.mdWriting radio advertisement scripts

Setup and Dependencies
ToolRequired byHow to installPython 3.8+All scriptshttps://www.python.org/downloads/yt-dlpscript1.pypip install yt-dlpffmpegclip_batch.pybrew install ffmpegNothing extraTRANSCRIPT_TOOL_v2.pyNo install needed

How to Add Something New
Adding a new script:

Put it in the scripts/ folder
Name it using lowercase and underscores: what_it_does.py
Add a section for it in this README under Scripts

Adding a new skill:

Put it in the skills/ folder
Name it: skill_name.md
Add a row for it in the Skills table above


Cloning This Repo
git clone https://github.com/sakshijayani24-collab/content-production-manager.git
