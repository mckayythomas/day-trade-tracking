# 📈 Day Trading Journal App

A full-stack journaling and analytics platform for active traders. This app allows users to record and track trades, document strategy reflections, and visualize performance trends over time using a clean calendar-based UI.

---

## 🌐 Live Demo

🔗 [Hosted App Link](https://your-live-demo-link.com)

---

## 🛠 Tech Stack

- **Frontend:** Next.js, Tailwind CSS, TypeScript
- **Backend:** Supabase (PostgreSQL, Auth)
- **Auth:** OAuth (Google, GitHub, Microsoft, Apple)
- **State Management:** React Hooks / Context
- **Calendar Visualization:** React-Calendar or similar
- **Deployment:** Docker, Supabase Hosting, Vercel (optional)

---

## ✨ Key Features

- 🧠 OAuth login (Google, GitHub, Apple, Microsoft)
- 📊 Record and manage trades with rich metadata
- 🗓️ Calendar view to visualize daily P/L with color coding (green/red)
- 🧾 Strategy journal for tracking systematic trading approaches
- 🔍 Filter trades by tag or strategy
- 🔐 User-based data isolation using Supabase row-level security (RLS)
- ⚙️ Easy Docker setup for local development

---

## 🧱 Data Models

### `users`
- `id` (UUID, from Supabase Auth)
- `email` (string)
- `created_at` (timestamp)

### `trades`
- `id` (UUID)
- `user_id` (FK to `users`)
- `symbol` (string)
- `entry_price` (decimal)
- `exit_price` (decimal)
- `position_size` (decimal)
- `date` (date)
- `result` (decimal)
- `tags` (array)
- `notes` (text)
- `screenshot_url` (string, optional)

### `strategies`
- `id` (UUID)
- `user_id` (FK to `users`)
- `name` (string)
- `rules` (text)
- `created_at` (timestamp)

---

## 🧑‍💻 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/day-trading-journal.git
cd day-trading-journal
```

---

### 2. Create a `.env.local` File

```bash
# .env.local
NEXT_PUBLIC_SUPABASE_URL=https://xyzcompany.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```

> You can find these keys in your Supabase project settings.

---

### 3. Docker Setup (Optional but Recommended)

#### Build and Run

```bash
docker-compose up --build
```

> This will start the app on `http://localhost:3000`

---

### 4. Run Locally without Docker

```bash
npm install
npm run dev
```

---

### 5. Supabase Setup

1. Create a [Supabase](https://supabase.io) project
2. Create tables using Supabase UI or SQL editor (see schema above)
3. Enable OAuth logins under **Authentication > Providers**
4. Configure row-level security (RLS) with policies to isolate user data
5. Paste project keys into `.env.local`

---

## 🚀 Planned Features

* Automatic trade import from brokers (via API)
* Visual stats dashboard (win rate, profit factor, etc.)
* Community forum + leaderboard
* Strategy performance analysis
* Mobile-first design

---

## 📦 Deployment

You can deploy this app using:

* **Vercel** (easy Next.js hosting)
* **Render** or **Railway** (Docker support)
* **Self-hosted VPS** via Docker

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## 📄 License

MIT License
