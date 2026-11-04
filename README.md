<div align="center">

# 💸 Smart Expense Tracker

**Track every rupee. Understand where your money goes.**

A full-stack personal finance app with secure login, income & expense management, a live dashboard and monthly reports.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open%20App-4f46e5?style=for-the-badge&logo=render&logoColor=white)](https://your-app-name.onrender.com)

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4-000000?logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/Auth-JWT-000000?logo=jsonwebtokens&logoColor=white)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?logo=chartdotjs&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue)

[Features](#-features) • [How it works](#-how-it-works) • [Getting started](#-getting-started) • [Deploy for free](#-deploy-for-free) • [API](#-api-reference) • [Roadmap](#-roadmap) • [Author](#-author)

</div>

---

## ✨ Features

| | Feature | What you get |
|---|---|---|
| 🔐 | **Register & Login** | Passwords hashed with bcrypt, sessions with JWT. Every user sees only their own data. |
| ➕ | **Add / Edit / Delete** | Full control over income and expense entries. |
| 🏷️ | **Categories** | Ready-made categories for income and expenses, plus your own custom ones. |
| 📊 | **Dashboard** | Total income, total expenses and balance at a glance, with this month's spending chart. |
| 🧾 | **Transaction history** | Search and filter by type, category and date range. |
| 📅 | **Monthly report** | Pick any month to see totals, category-wise spending and a 12-month income vs expense chart. |
| 🗄️ | **Database** | All data is stored in PostgreSQL, so nothing is lost on restart. |
| 📱 | **QR code** | Generate a QR code of the live website from inside the app, ready to share. |

## 🧠 How it works

```mermaid
flowchart LR
    A[Browser<br/>HTML, CSS, JS] -->|REST API + JWT| B[Express server]
    B --> C[(PostgreSQL)]
    B --> D[bcrypt + JWT<br/>authentication]
```

## 🛠️ Tech stack

- **Frontend:** HTML, CSS, vanilla JavaScript, Chart.js
- **Backend:** Node.js, Express
- **Database:** PostgreSQL (`pg`)
- **Auth:** bcryptjs, JSON Web Tokens
- **Hosting:** Render (app) + Neon (database), both on free plans

## 🚀 Getting started

**You need:** Node.js 18 or above, and a free PostgreSQL database from [Neon](https://neon.com).

```bash
# 1. Clone the repo
git clone https://github.com/SatyamxBuilds/expense-tracker.git
cd expense-tracker

# 2. Install dependencies
npm install

# 3. Create your .env file
cp .env.example .env        # on Windows: copy .env.example .env
```

Open `.env` and fill in:

```env
PORT=3000
JWT_SECRET=any-long-random-text
DATABASE_URL=postgresql://user:password@host/dbname?sslmode=require
```

```bash
# 4. Start the app
npm start
```

Open **http://localhost:3000**, create an account and start tracking. The database tables are created automatically on the first run.

## ☁️ Deploy for free

1. Push this repo to your GitHub account.
2. Create a free Postgres database on **Neon** and copy the connection string.
3. On **Render**, choose **New → Blueprint** and select the repo (it reads `render.yaml`).
4. Add the `DATABASE_URL` environment variable. `JWT_SECRET` is generated automatically.
5. When the deploy finishes, open your link, click **QR code** and download the QR.

> Free Render services sleep after some idle time, so the first load can take about a minute.

## 📡 API reference

All routes except `/api/auth/*` need the header `Authorization: Bearer <token>`.

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Create an account |
| `POST` | `/api/auth/login` | Login and get a token |
| `GET` `POST` | `/api/categories` | List or add categories |
| `DELETE` | `/api/categories/:id` | Delete an unused category |
| `GET` `POST` | `/api/transactions` | List (filters: `type`, `category_id`, `from`, `to`, `q`) or add |
| `PUT` `DELETE` | `/api/transactions/:id` | Edit or delete a transaction |
| `GET` | `/api/summary?month=YYYY-MM` | Totals and category breakdown (leave month empty for all time) |
| `GET` | `/api/reports/monthly?year=YYYY` | Income vs expense for each month |

## 📁 Project structure

```
expense-tracker/
├── server.js            # app entry point
├── db.js                # database connection and tables
├── render.yaml          # one-click deploy settings for Render
├── middleware/
│   └── auth.js          # verifies the login token
├── routes/
│   ├── auth.js          # register and login
│   └── data.js          # categories, transactions, summary, reports
└── public/              # frontend
    ├── index.html
    ├── style.css
    └── app.js
```

## 🗺️ Roadmap

- [x] Register and login
- [x] Add, edit and delete transactions
- [x] Categories
- [x] Dashboard, history and monthly report
- [x] PostgreSQL integration
- [x] QR code sharing
- [ ] Export to CSV
- [ ] Budget limit for each category
- [ ] Recurring transactions
- [ ] Dark mode

## 🤝 Contributing

Ideas and pull requests are welcome. Fork the repo, create a branch, make your change and open a pull request.

## 👨‍💻 Author

**Satyam Pandey**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Satyam%20Pandey-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/satyamxpandey26)
[![GitHub](https://img.shields.io/badge/GitHub-SatyamxBuilds-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SatyamxBuilds)

---

<div align="center">

If this project helped you, please give it a ⭐

Made with ❤️ by [Satyam Pandey](https://www.linkedin.com/in/satyamxpandey26)

</div>
