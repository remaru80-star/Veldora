📁 Advanced Auto Rename Bot 🤖
<p align="center"> <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python"/> <img src="https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"/> <img src="https://img.shields.io/badge/MongoDB-Database-green?style=for-the-badge&logo=mongodb" alt="MongoDB"/> <img src="https://img.shields.io/badge/FFmpeg-Metadata-007808?style=for-the-badge&logo=ffmpeg" alt="FFmpeg"/> <img src="https://img.shields.io/badge/Pyrogram-2.0.106-orange?style=for-the-badge" alt="Pyrogram"/> <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License"/> </p><p align="center"> <b>The ultimate Telegram bot for renaming, tagging, and ordering your media files – automatically.</b><br> <i>Private chat only · Queue-based · Metadata injection · Thumbnails · Sequence sorting · Failed-file recovery</i> </p>
🌟 What Can This Bot Do?
🔁 Auto‑rename files using a custom template with dynamic variables like {season}, {episode}, {quality}, etc.

🖼️ Set persistent thumbnails – every renamed file gets your chosen image.

🏷️ Embed metadata (title, author, artist, video/audio track titles) via FFmpeg – no re‑encoding!

📬 Process files one‑by‑one through a priority queue (admins jump ahead).

🔢 Sort entire seasons/episodes with sequence mode (3 sort styles), then rename them in perfect order.

🆘 Manual rename fallback – if the bot can’t extract season/episode, it saves the file and asks you to name it later.

🎚️ Choose output type – Document, Video or Audio – with a single tap.

👑 Admin tools – pause/resume queue, broadcast, clear queues, view stats.

🧠 How It Works (Step‑by‑Step)

















Set your rename template with /autorename, e.g. /autorename {filename} [S{season}E{episode}] - {quality}

Send a file – the bot extracts season, episode, and quality from the filename using smart regex.

If extraction succeeds → the file is downloaded, metadata is added, the thumbnail is attached, and it’s renamed and sent back.

If extraction fails → the file goes to your failed queue. Once all other tasks finish, the bot will ask you to provide a new filename manually.

Sequence mode lets you collect many files first (/ssequence), sort them (/esequence) and then add them to the processing queue in the exact order you want.

⚙️ Environment Variables – How to Set Them
The bot reads all configuration from a .env file (or environment variables on cloud hosts).
Create a file named .env in the same folder as the bot script and paste the following:
API_ID = 123456
API_HASH = your_api_hash
BOT_TOKEN = 123:abc...
ADMIN = 111111,222222
DB_URL = mongodb+srv://user:pass@cluster.mongodb.net
DB_NAME = mydb
LOG_CHANNEL = -1001234567890
START_PIC = https://example.com/pic.jpg   # optional
WEBHOOK = true                            # optional
PORT = 8080                               # optional
🔒 Never share your .env file or commit it to version control!

💾 Installation & Running
🔹 Deploy to Heroku (one‑click)
https://www.herokucdn.com/deploy/button.svg

Click the button above.

Fill in all the required Config Vars (same as the .env keys).

Deploy the app and turn on the worker dyno (not web).

Your bot is live!

🔹 Run on a VPS (Linux / Ubuntu)
bash
# 1. Install system dependencies
sudo apt update
sudo apt install python3 python3-pip ffmpeg -y

# 2. Clone the repository
git clone https://github.com/yourusername/advanced-rename-bot.git
cd advanced-rename-bot

# 3. Install Python packages
pip3 install -r requirements.txt

# 4. Create and edit the .env file
nano .env          # Paste your variables, save and exit

# 5. Start the bot (use a process manager like tmux or screen for 24/7)
python3 bot02_simplified.py
🔹 Local Development (Windows / macOS)
Install Python 3.8+, FFmpeg, and MongoDB (local or Atlas).

Clone the repo and install dependencies as above.

Place your .env file in the project root.

Run python bot02_simplified.py.

🧪 Usage Examples
🎯 Basic Rename
Set a format once, and all files will follow it:

text
/autorename {filename} [S{season}E{episode}] - {quality}
File: MyShow S01E03 1080p.mkv → MyShow [S01E03] - 1080p.mkv

🎞 Custom Caption
text
/set_caption {filename} | {filesize} | {duration}
🖼 Thumbnail
Send a photo to the bot.

Reply to it with /set_thumbnail.

All subsequent files will carry that thumbnail.

🏷 Metadata Injection
/settitle My Show Title

/setauthor @MyChannel

/setallmeta @AnimeMultiDub (sets all metadata fields at once)

🔢 Sequence Sorting
/ssequence – start collecting files.

Send all episode files.

/esequence – choose how to sort them (e.g., Season → Quality → Episode).

The bot forwards them in the correct order, then asks if you want to add them to the rename queue – tap “Add to Queue”.

🆘 Failed File Recovery
If a file couldn’t be auto‑renamed, the bot will notify you. After all your queued files finish, it will send:

text
Select The Output File Type File Name :- MyStrangeFile.mp4
Please Enter New Filename...
Simply type the new name (without extension) and the bot will process it immediately.

🛠️ Admin Commands
Command	Effect
/stop_renaming	Pause the processing queue (files still accepted)
/start_renaming	Resume processing
/admin_priority_on / _off	Enable/disable admin priority
/clear_queue	Remove all waiting tasks (current task continues)
/clear_queue_user 123456	Clear a specific user’s queue
/stats	Show bot uptime, user count, queue stats
/broadcast	Send a message to all bot users
🚨 Troubleshooting
Problem	Solution
FFmpeg not found	Install FFmpeg (sudo apt install ffmpeg) or ensure it’s in your PATH
MongoDB connection error	Check your DB_URL – ensure IP whitelisting is correct on Atlas, or that local MongoDB is running
Bot doesn’t respond	Verify API_ID, API_HASH, BOT_TOKEN are correct; ensure you started the bot with python bot02_simplified.py
Files not being renamed	You must first set a rename format with /autorename
Metadata not appearing	Enable metadata with /metadata (toggle ON) – it is enabled by default
🤝 Support & Community
📢 Updates Channel: @AnimeMultiDub

🆘 Support Group: @AnimeMultiDub (edit link if needed)

🐞 Bug Report: Open an issue on GitHub

<p align="center"> <b>⭐ Star this repository if you find it useful! ⭐</b><br> Built with ❤️ by <a href="https://t.me/AnimeMultiDub">@AnimeMultiDub</a> </p>
