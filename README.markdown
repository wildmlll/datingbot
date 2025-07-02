# DateBot 💌

A fun and interactive Telegram bot built with **Python** and **aiogram**, designed to help users create and share dating profiles, connect with others, and find matches based on their preferences. Powered by a SQLite database, this bot offers a simple yet engaging way to meet new people in a Telegram environment.

This pet project was created to showcase my skills in Python development and Telegram bot creation.

## ✨ Features

- **User Profiles**: Create a dating profile with details like name, age, city, gender, and a photo, along with a short bio.
- **Matchmaking**: Browse random profiles based on your preferences (gender, age, city) and react with "Like" or "Skip."
- **Ephemeral Interaction**: Like a profile to notify the other user and share your Telegram handle for direct communication.
- **Profile Management**: Edit your profile text, update your photo, or delete your profile entirely.
- **Channel Subscription Check**: Ensures users are subscribed to a specific Telegram channel for access to the bot's features.

## 🛠️ Tech Stack

- **Backend**: Python, aiogram (Telegram Bot API framework)
- **Database**: SQLite for storing user profiles and preferences
- **Storage**: Local file storage for user-uploaded photos
- **Deployment**: Python script running with a Telegram bot token

## 🚀 Getting Started

Follow these steps to set up and run DateBot locally.

### Prerequisites

- Python 3.8 or higher
- Telegram Bot Token (obtained from [BotFather](https://t.me/BotFather))
- SQLite database setup
- pip for installing dependencies

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/wildmlll/datingbot
   cd datingbot
   ```

2. **Install dependencies**:
   ```bash
   pip install aiogram
   ```

3. **Set up the Telegram Bot**:
   - Create a bot via [BotFather](https://t.me/BotFather) and obtain the API token.
   - Update the bot token in `bot.py`:
     ```python
     bot = Bot(token="BOTAPI")
     ```

4. **Set up the SQLite database**:
   - Ensure a SQLite database file (`database.db`) is created in the project directory.
   - The bot uses a `BotDB` class (assumed to be defined in `db.py`) to manage user data and profiles. Ensure the database schema includes tables for users and profiles with fields for `user_id`, `gender`, `interest`, `name`, `age`, `city`, and `text`.

5. **Create a photos directory**:
   - Create a `photos` folder in the project directory to store user-uploaded images:
     ```bash
     mkdir photos
     ```

6. **Run the bot**:
   ```bash
   python bot.py
   ```

### Database Setup

- Ensure the `BotDB` class in `db.py` handles:
  - User registration (`add_user`, `user_exists`)
  - Profile creation and management (`add_anketa`, `get_anketa`, `update_text`, `delete_anketa`)
  - Profile matching (`find_anketi` based on user preferences)
- Set up the SQLite database with the necessary tables and indexes for efficient querying.

### Telegram Channel Setup

- Create a Telegram channel for subscription checks (e.g., `https://t.me/testkurilka1`).
- Update the `chat_id` in the bot’s subscription check logic:
  ```python
  member = await bot.get_chat_member(chat_id=-1002019990616, user_id=message.from_user.id)
  ```
  Replace `-1002019990616` with your channel’s chat ID.

## 📱 Running the Bot

- Start the bot with `python bot.py`.
- Open Telegram and interact with your bot using the `/start` command.
- Follow the prompts to create a profile, browse other profiles, or manage your existing profile.

## 📄 License

Copyright (c) 2025 Maksym Hanych

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall his permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## 🙌 Acknowledgments

- [aiogram](https://github.com/aiogram/aiogram) for the powerful Telegram Bot framework.
- [SQLite](https://www.sqlite.org/) for lightweight and reliable database storage.
- All users and testers of DateBot! 💖

---

🌟 **DateBot** - Connect, like, and start chatting in a fun and simple way!
