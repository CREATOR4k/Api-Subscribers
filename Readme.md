# GitHub Followers Analyzer 📊

A simple and efficient Python script for analyzing your GitHub followers and the users you follow, using the official GitHub REST API.

The script helps you quickly tidy up your profile by identifying:
*   **Mutual connections** — users who follow you and whom you also follow.
*   **One-way following** — users you follow who do not follow you back.
*   **Fans** — users who follow you, but whom you do not follow back.

## ✨ Features
 
*   **Comprehensive data retrieval:** Automatically handles GitHub API pagination, allowing it to fetch lists of any size (even those with more than 100 users).
*   **Direct links:** Outputs results as clickable links to user profiles.
*   **Security and rate limits:** Can run without authentication (up to 60 requests per hour) or with a GitHub Personal Access Token to bypass rate limits.

## 🚀 Getting Started

### 1. Setting up the environment

Ensure you have Python 3.x and the `requests` library installed. If you don't have the library, install it via:

```bash
pip install requests
```

### 2. Configuring the script

Open the script file and edit the constants at the top:

```python
# Enter your GitHub username
USERNAME = "Your_Username"

# (Optional) Enter your GitHub Personal Access Token if you have a large number of followers/following.
# Leave as an empty string "" to run without a token.
TOKEN = ""
```

> **Note:** If the total number of your followers and the users you follow exceeds 60 pages of data, GitHub will block requests made without an authentication token. To create a token, go to *Settings -> Developer Settings -> Personal access tokens -> Tokens (classic)* and generate a token with at least the **`read:user`** permission.

### 3. Execution

Run the script via your terminal or command line:

```bash
python main.py
```

## 📋 Example Output

```text
Retrieving data for account CREATOR4k...

📊 Profile Statistics:
Followers: 45
Following: 50
Mutual connections: 30

❌ You are following them, but they are NOT following you back (20):
- https://github.com
- https://github.com

⭐ They are following you, but you are NOT following them back (15):
- https://github.com
```

## 🛠️ Tech Stack

*   Python 3
*   `requests` library
*   GitHub REST API v3
