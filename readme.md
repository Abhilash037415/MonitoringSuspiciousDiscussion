# 🕵️ Monitoring Suspicious Discussions (MSD)

Welcome to **Monitoring Suspicious Discussions (MSD)**!
This project automatically detects and flags potentially harmful or suspicious conversations in online forums using NLP.

---

## 🤔 What is MSD?

**Monitoring Suspicious Discussions (MSD)** is an intelligent moderation tool that:

* Automatically scans forum posts.
* Detects violent, abusive, or inappropriate content.
* Flags content for admin review only when necessary.

Built using **Flask**, **Jinja2**, and **MySQL**, it's fast, reliable, and super easy to use.

---

## 🛠️ Software Requirements

To run MSD locally, you’ll need:

* Python 3.x
* Flask
* MySQL Server
* VS Code or any IDE
* Web Browser (Chrome recommended)

---

## 📂 Setting Up MSD on Your System

1. Clone or download the repository.

2. Ensure the following structure exists:

   * `templates/` – Jinja2 HTML files
   * `app.py` – Flask server script
   * `msd.sql` – Database schema
   * `suspicious_model/` – (Optional) Custom logic/ML models

3. In MySQL:

   * Create a database named `msd`.
   * Import the `msd.sql` file to initialize tables like `users`, `posts`, and `admins`.
   * (Recommended) Register users and create posts using the UI instead of inserting directly.

---

## ▶️ Running MSD

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. (One-time) Download NLTK data:

   ```python
   import nltk
   nltk.download('vader_lexicon')
   ```

3. Configure your `.env` file with DB credentials:

   ```env
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_password
   DB_NAME=your_db_name
   ```

4. Run the server:

   ```bash
   python app.py
   ```

5. Open your browser:

   ```
   http://localhost:5000/
   ```

---

## 💡 How MSD Works

1. Users can **register or log in** as either:

   * Normal users
   * Admins

2. Users can submit new posts.

3. Each post is analyzed for:

   * Suspicious keywords using fuzzy matching and stemming
   * Sentiment score using VADER

4. Based on the score:

   * Good posts are published.
   * Moderately suspicious posts go to **Admin Review**.
   * Highly offensive posts are marked **deleted**.

5. Admins can:

   * View flagged posts
   * Approve or delete them
   * Affect user scores based on actions

---

## 👥 Project Contributors

This project was built with ❤️ by:

* [Abhilash037415](https://github.com/Abhilash037415)
* [AlapatiVamsi05](https://github.com/AlapatiVamsi05)
* [VarunSai2005](https://github.com/VarunSai2005)
* [ksamuel-soul](https://github.com/ksamuel-soul)
* [rohitsripathi9](https://github.com/rohitsripathi9)

---

## 🧼 Final Thoughts

> We designed MSD to **protect online spaces** from harmful content while minimizing manual moderation work.
>
> No subscriptions. No bullshit. Just clean content detection.

Stay safe and don’t be sus. 🕶️
