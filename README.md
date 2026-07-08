# 📁 Advanced Auto Rename Bot 🤖

<p align="center">

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![FFmpeg](https://img.shields.io/badge/FFmpeg-Metadata-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![Pyrogram](https://img.shields.io/badge/Pyrogram-2.x-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

</p>

<p align="center">

## Rename • Tag • Sort • Organize

**A powerful Telegram bot that automatically renames, tags, sorts, and manages your media files with support for thumbnails, FFmpeg metadata, smart queues, sequence sorting, and much more.**

**Private Chat Only • Queue System • Metadata Injection • Episode Sorting • Manual Recovery**

</p>

---

# ✨ Features

## 📂 Smart Auto Rename

Automatically rename files using custom templates.

Example:

```text
{filename} [S{season}E{episode}] - {quality}
```

Supported variables:

- `{filename}`
- `{season}`
- `{episode}`
- `{quality}`
- `{year}`
- `{audio}`
- `{language}`
- `{extension}`

---

## 🖼 Persistent Thumbnail

- Set your thumbnail once.
- Every renamed file automatically uses it.
- Supports videos and documents.

---

## 🏷 FFmpeg Metadata

Embed metadata **without re-encoding**.

Supports:

- Title
- Author
- Artist
- Album
- Video Track
- Audio Track
- Description

---

## 🔢 Sequence Sorting

Rename an entire season in perfect order.

Supports:

- Season → Episode
- Episode Only
- Quality → Episode
- Custom Sorting

---

## 📬 Queue System

Every user gets their own queue.

Features:

- FIFO processing
- Admin Priority
- Pause/Resume
- Queue Statistics
- Queue Cleanup

---

## 🎚 Output Type Selection

Choose how Telegram uploads your file.

- 📄 Document
- 🎥 Video
- 🎵 Audio

---

## 🆘 Failed File Recovery

If the bot cannot determine season or episode:

- Saves the file
- Continues processing the queue
- Asks for a manual filename afterwards

No file is lost.

---

# 🚀 Workflow

```text
User Sends File
       │
       ▼
Extract Information
       │
       ├── Success
       │      │
       │      ▼
       │ Rename
       │ Add Metadata
       │ Add Thumbnail
       │ Upload
       │
       ▼
Finished

       OR

Extraction Failed
       │
       ▼
Move To Failed Queue
       │
       ▼
Queue Completes
       │
       ▼
Ask User For Filename
       │
       ▼
Rename & Upload
```

---

# ⚙ Environment Variables

Create a `.env` file.

```env
API_ID=123456
API_HASH=xxxxxxxxxxxxxxxxxxxx
BOT_TOKEN=123456:ABCDEF

ADMIN=11111111,22222222

DB_URL=mongodb+srv://username:password@cluster.mongodb.net

DB_NAME=RenameBot

LOG_CHANNEL=-100123456789

START_PIC=https://example.com/image.jpg

WEBHOOK=True
PORT=8080
```

> **Never share your `.env` file.**

---

# 💻 Installation

## Ubuntu / VPS

### Install dependencies

```bash
sudo apt update
sudo apt install python3 python3-pip ffmpeg -y
```

### Clone Repository

```bash
git clone https://github.com/remaru80-star/Veldora.git

cd Veldora
```

### Install packages

```bash
pip3 install -r requirements.txt
```

### Configure

```bash
nano .env
```

Paste your variables.

### Start Bot

```bash
python3 bot02_simplified.py
```

For production, use:

- systemd
- screen
- tmux

---

# ☁ Deploy to Heroku

Click the Deploy button.

Fill all Config Vars.

Start the **Worker Dyno**.

---

# 🧪 Usage

## Set Rename Format

```text
/autorename {filename} [S{season}E{episode}] - {quality}
```

Example

```
Input

My Show S01E05 1080p.mkv

↓

Output

My Show [S01E05] - 1080p.mkv
```

---

## Caption

```text
/set_caption

{filename}

{filesize}

{duration}
```

---

## Thumbnail

1. Send Photo
2. Reply

```text
/set_thumbnail
```

Done.

---

## Metadata

Set Title

```text
/settitle My Awesome Series
```

Author

```text
/setauthor @AnimeMultiDub
```

Everything

```text
/setallmeta @AnimeMultiDub
```

---

## Sequence Mode

```text
/ssequence
```

Send every episode.

When finished

```text
/esequence
```

Choose a sorting method.

Finally

**Add To Queue**

---

## Failed Files

If extraction fails you'll receive

```text
Select Output Type

Filename:
MyMovie.mkv

Please Enter New Filename...
```

Type

```text
My Movie Episode 01
```

The bot finishes automatically.

---

# 👑 Admin Commands

| Command | Description |
|----------|-------------|
| `/stop_renaming` | Pause Queue |
| `/start_renaming` | Resume Queue |
| `/admin_priority_on` | Enable Admin Priority |
| `/admin_priority_off` | Disable Admin Priority |
| `/clear_queue` | Clear All Waiting Jobs |
| `/clear_queue_user ID` | Clear User Queue |
| `/broadcast` | Broadcast Message |
| `/stats` | Bot Statistics |

---

# ❓ Troubleshooting

| Problem | Solution |
|----------|----------|
| FFmpeg not found | Install FFmpeg |
| MongoDB Error | Check `DB_URL` and Atlas whitelist |
| Bot Offline | Verify API credentials |
| Rename doesn't work | Set `/autorename` first |
| Metadata missing | Enable `/metadata` |

---

# 📦 Requirements

- Python 3.8+
- FFmpeg
- MongoDB
- Pyrogram
- TgCrypto (Recommended)

---

# 📊 Main Features

- ✅ Smart Regex Detection
- ✅ Auto Rename
- ✅ Queue System
- ✅ Admin Priority
- ✅ Metadata Injection
- ✅ Thumbnail Support
- ✅ Caption Templates
- ✅ Sequence Sorting
- ✅ Failed File Recovery
- ✅ Document / Video / Audio Output
- ✅ MongoDB Storage
- ✅ Logging
- ✅ Broadcast
- ✅ Statistics
- ✅ Multi-user Support

---

# 📢 Support

**Updates Channel**

https://t.me/AnimeMultiDub

**Support Group**

https://t.me/AnimeMultiDub

**Issues**

Open an issue on GitHub.

---

# ❤️ Credits

Developed with ❤️ by **AnimeMultiDub**

---

<p align="center">

## ⭐ If this project helped you, please give it a Star!

It motivates future development and improvements.

</p>
