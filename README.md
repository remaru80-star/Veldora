📁 Auto Rename Bot — Advanced Telegram File Renamer
<p align="center"> <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python" /> <img src="https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=for-the-badge&logo=telegram" /> <img src="https://img.shields.io/badge/MongoDB-Database-green?style=for-the-badge&logo=mongodb" /> <img src="https://img.shields.io/badge/FFmpeg-Metadata-007808?style=for-the-badge&logo=ffmpeg" /> <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" /> </p><p align="center"> <b>Effortlessly rename, tag, and sort your media files directly in Telegram private chat</b><br> <i>Queue‑based • Metadata • Thumbnails • Sequence Sorting • Manual Rename Recovery</i> </p>
✨ What Can It Do?
🔄 Smart Auto-Rename – Use dynamic variables like {season}, {episode}, {quality} to create any filename format.

🖼️ Custom Thumbnails – Attach a persistent thumbnail to every renamed file.

🏷️ Metadata Injection – Embed title, author, artist, audio/video track info via FFmpeg (no re‑encoding).

📋 Queue System – All files are processed one‑by‑one. Admins get priority. Pause/resume anytime.

🔢 Sequence Sorting – Collect a bunch of episodes, sort them by season→episode→quality (or 2 other modes), then rename them in perfect order.

🆘 Manual Rename Fallback – If extraction fails, the file is saved; the bot prompts you to name it later.

🎚️ Output Type Choice – Send as Document, Video, or Audio with a button tap.

👑 Admin Tools – Broadcast, clear queues, toggle admin priority, view stats.

🧠 How It Works
Set a rename format → /autorename {filename} [S{season}E{episode}] - {quality}

Send a file → Bot extracts season, episode, quality from the filename.

If successful → Downloads file → Adds metadata → Applies thumbnail → Renames → Sends back.

If extraction fails → File goes to failed queue. When all other tasks finish, bot asks you to type a new name manually.

Sequence Mode → Save files (/ssequence), choose sort mode (/esequence), then add them to the queue in the exact order you want.

🎯 Everything happens in private chat – simple, fast, and secure.

⚙️ Environment Variables
Create a .env file in the project root with the following keys:

ini
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
Variable	Required	Purpose
API_ID	✅	Telegram API ID – obtain from my.telegram.org
API_HASH	✅	Telegram API Hash
BOT_TOKEN	✅	Bot token from @BotFather
ADMIN	✅	Admin user IDs (comma‑separated, no spaces)
DB_URL	✅	MongoDB connection string (local or Atlas)
DB_NAME	✅	MongoDB database name
LOG_CHANNEL	✅	Telegram channel/group ID where startup logs are sent
START_PIC	❌	Image URL shown in /start (skip for text‑only)
WEBHOOK	❌	Set to true to use webhook instead of polling
PORT	❌	Required only if WEBHOOK = true
🔒 Never share your .env file publicly!

🚀 How to Run
🟢 Deploy on Heroku (one‑click)
https://www.herokucdn.com/deploy/button.svg

Click the button and fill the Config Vars (same as .env keys).

Deploy, then enable the worker dyno (not web).

Done! Bot starts instantly.

🟡 Run on a VPS (Ubuntu)
bash
sudo apt update && sudo apt install python3 python3-pip ffmpeg -y
git clone https://github.com/yourusername/your-repo
cd your-repo
pip3 install -r requirements.txt
nano .env            # add your variables
python3 bot02_simplified.py
To keep it running 24/7, use tmux or screen.

🔵 Local Development (Windows/macOS)
Install Python 3.8+, FFmpeg, and MongoDB.

Clone repo, install dependencies, create .env, run python bot02_simplified.py.

🧪 Usage Examples
Command	Result
/autorename {filename} [S{season}E{episode}] - {quality}	MyShow S01E03 1080p.mkv → MyShow [S01E03] - 1080p.mkv
/set_thumbnail (reply to a photo)	All future files use that photo as thumbnail
/settitle My Series	Injects “My Series” into file metadata
/ssequence → send files → /esequence	Sorts episodes, then renames them in order
/failed_queue	Shows files that need manual naming
🛠️ Admin Commands
Command	Action
/stop_renaming / /start_renaming	Pause / resume the queue
/admin_priority_on / _off	Toggle admin priority in queue
/clear_queue	Empty the whole waiting queue
/clear_queue_user 123456	Remove a user’s queued files
/stats	Bot uptime, users, queue summary
/broadcast	Send a message to all bot users
🤝 Support
📢 Channel: @AnimeMultiDub

🆘 Group: @AnimeMultiDub (edit link)

🐞 Issues: GitHub Repo

<p align="center"> ⭐ Star the repo if it helps you!<br> Made with ❤️ by <a href="https://t.me/AnimeMultiDub">@AnimeMultiDub</a> </p>
