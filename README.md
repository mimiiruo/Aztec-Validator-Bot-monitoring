# Aztec Validator Monitor Bot for Telegram

A simple yet powerful Telegram bot built with Python to monitor validator status on the Aztec network. Get automatic notifications for important activities and check your validator's status anytime with a simple command.

## ✨ Key Features

### 🔔 Automatic Notifications
Get real-time alerts directly in Telegram whenever your validator:
- ✍️ Successfully submits an attestation
- ⚠️ Misses an attestation  
- ✅ Successfully proposes a block

### 📊 Manual Status Checks
Use the `/check` command to get a full status report at any time, which includes:
- Validator Rank
- Status (e.g., Validating/Offline)
- Total Balance & Rewards
- Attestation & Block Proposal Success Rates
- Epoch Participation & Voting History Count

### Additional Features
- 🔗 **Direct Links**: Each status report includes a direct link to the validator's dashboard on dashtec.xyz
- 🔒 **Secure & Private**: The bot will only respond to commands from your specified Telegram ID
- ⚙️ **Easy Management**: Easily add, remove, and view validators with `/add`, `/remove`, and `/list` commands
- ⚡ **Lightweight**: Designed to run efficiently on a server (VPS) with minimal resource consumption

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8 or newer
- A server/VPS or a computer that can run 24/7
- A Telegram account

### Step 1: Clone the Repository
```bash
git clone https://github.com/skyhazee/aztec-validator-monitor.git
cd aztec-validator-monitor
```

Create a screen session:
```bash
screen -S aztecbot
```

### Step 2: Set Up a Virtual Environment (Recommended)
```bash
# Create the environment
python3 -m venv venv

# Activate the environment
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Configure the Bot

#### Get your Bot Token:
1. Open Telegram and start a chat with `@BotFather`
2. Send the `/newbot` command and follow the instructions to create a new bot
3. BotFather will give you a unique token. Copy it.

#### Get your Telegram User ID:
1. Start a chat with `@userinfobot`
2. Send the `/start` command
3. The bot will reply with your User ID. Copy it.

#### Create the .env file:
```bash
nano .env
```

Add your credentials:
```env
# Paste the token you got from @BotFather
BOT_TOKEN="123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11"

# Paste your User ID you got from @userinfobot
TELEGRAM_ID="123456789"
```

Press `Ctrl+X`, then `Y` to save.

### Step 5: Run the Bot
```bash
python bot.py
```

If you see no errors, your bot is now online! For continuous operation, it's recommended to use a process manager like `screen` or `tmux`.

## 🤖 How to Use the Bot

Interact with your bot by sending these commands in your private chat:

| Command | Description |
|---------|-------------|
| `/start` | Displays a welcome message and summary of functions |
| `/add <validator_address>` | Adds a validator address to monitoring list |
| `/remove <validator_address>` | Removes a validator address from monitoring list |
| `/list` | Shows all validator addresses you're monitoring |
| `/check` | Requests full status report for all validators |

### Example Usage
- `/add 0x123abc...`
- `/remove 0x123abc...`

## 📊 Example Output

### /check Command Response
```
👑 Rank: 1
📊 Status Validator: 0x...
Validating ✅
💰 Saldo: 100.00 STK
🏆 Total Rewards: 500.00 STK
-----------------------------------
✨ Performance Metrics
🛡️ Attestation Rate: 95.8%
    1150 Succeeded / 50 Missed
📦 Block Proposal Rate: 94.1%
    32 Proposed or Mined / 2 Missed
🗓️ Epoch Participation: 46
🗳️ Jumlah Voting: 10
```

### Attestation Notifications
**Missed Attestation:**
```
⚠️ Atestasi Terlewat
Validator: 0x... | Slot: #50432
Hasil: Missed
```

**Successful Attestation:**
```
✍️ Atestasi Sukses
Validator: 0x... | Slot: #50433
Hasil: Success
```

**Successful Block Proposal:**
```
✅ Proposal Blok Sukses!
Validator: 0x... | Slot: #50448
Status: BLOCK-MINED
```

## 📁 Repository Structure
```
aztec-validator-monitor/
├── README.md
├── bot.py
├── last_state.json
├── requirements.txt
└── validators.json
```
