# ♠ EV Club Management System
### מערכת ניהול מועדון פוקר

A complete poker club management web application — runs entirely in the browser, no server required.

---

## 🚀 Getting Started

1. Download the repository
2. Open `index.html` in any modern browser (Chrome / Edge / Firefox)
3. That's it — no installation, no server, no internet required

---

## 📁 File Structure

```
ClubManagement/
├── index.html                    # Entry point — open this in browser
├── Poker Big Club.dc.html        # Main application (Design Component)
├── support.js                    # DC runtime (required)
├── README.md                     # This file
└── uploads/                      # Sample Excel files
    ├── 04.07.26.xlsx             # Cash game sample
    ├── 2026-07-04.xlsx           # Tournament sample
    └── debt.xlsx                 # Player debts sample
```

---

## ✨ Features

### 🃏 Cash Game Tracker
- Real-time Buy-In entry with player autocomplete
- Player database saved locally — grows with every session
- Close player with payment method: **מזומן / חוב / אשראי**
- Automatic debt update when player pays by חוב
- Live stats: players, total buy-ins, cashouts, gross profit, net profit

### 🎰 Dealers Management
- Dealer database with role, rate, active status
- Session dealer shifts: start/end time → hours auto-calculated
- Rake tracker per time slot (linked to dealer)

### 💸 Cash Expenses
- Rake tracker by time slot
- Staff wages (dealers + waitress)
- Bonuses with reason
- Rent field
- Net profit = Gross − Rake − Staff − Bonuses − Rent

### 🏆 Tournament Tracker
- Fully editable form matching Excel layout
- Entry types: כניסות מוקדמות, ריביי, אד-און, etc.
- Kitchen staff wages (time range → hours → salary)
- Floor staff wages
- Other expenses
- Auto-calculated: קופת פרסים, הכנסת בית, רווח נקי

### 💳 Debt Management
- Full player debt list
- Club financials: קופה ראשית, קופה קטנה, עו"ש, סליקה
- Search by player name
- Manual add/edit/delete

### 📊 Financial Summary (שינוי פיננסי)
- Full daily delta: cash flow, tournament flow, debt changes, receipts
- Balance sheet: all accounts in one view

### 🧾 Daily Receipts
- Category-based: אוכל, ציוד, ניקיון, הובלה, שונות
- Photo attachment per receipt (stored locally)
- Filter by category
- Running total

### 📋 Session History
- All cash sessions and tournaments
- Click to view full session details

### 👥 Players
- Full player database (62+ players)
- Shows debt status per player

### ⚙️ Settings
- Storage mode: **Local** / **Supabase** / **Both**
- Supabase connection config (URL + Anon Key)
- Sync: push local → Supabase / pull Supabase → local
- Salary rates: dealer rate, waitress rate
- Backup / Restore as JSON
- Dark / Light theme toggle

---

## 💾 Data Storage

| Where | What |
|---|---|
| `localStorage` | All session data, player DB, settings |
| Supabase (optional) | Cloud sync across devices |
| JSON backup | Full export/restore via file |

---

## 📥 Excel Import

Both cash and tournament screens support importing `.xlsx` files:
- **Cash:** reads player names, buy-ins, cashouts from your existing format
- **Tournament:** reads entry types, staff wages, other expenses

---

## ☁️ Supabase Setup (Optional)

For multi-device access:

1. Install Docker Desktop
2. Run:
   ```bash
   npm install -g supabase
   supabase init
   supabase start
   ```
3. Copy the API URL and Anon Key from terminal output
4. In the app → ⚙️ הגדרות → paste URL + Key → Save
5. Create table in Supabase Dashboard:
   ```sql
   CREATE TABLE pbc_data (
     key text PRIMARY KEY,
     value jsonb,
     updated_at timestamptz DEFAULT now()
   );
   ```

---

## 🛠️ Tech Stack

- **Pure HTML + JavaScript** — no framework, no build step
- **JSZip** — Excel file parsing (loaded from CDN)
- **SheetJS** — Excel export (planned)
- **Supabase JS v2** — optional cloud storage (loaded from CDN)
- **Heebo font** — Hebrew RTL typography (Google Fonts)

---

## 📱 Recommended Usage

- **Laptop/desktop** at the poker table
- Chrome or Edge browser
- Screen resolution: 1280px+ wide

---

## 🔄 Version History

| Date | Version | Notes |
|---|---|---|
| 08.07.2026 | v1.0 | Initial release |

---

## 📞 Support

Built with Claude AI — EV Club Management System
