# Simplify System

A cooperative information system built with Flutter (mobile) and Node.js + Prisma ORM (backend).

---

## Tech Stack

- **Frontend**: Flutter
- **Backend**: Node.js + Express
- **ORM**: Prisma
- **Database**: Microsoft SQL Server

---

## Project Structure

```
root/
├── backend/
│   ├── server.js
│   ├── prisma/
│   │   └── schema.prisma
│   ├── .env.example
│   └── package.json
└── flutter_project/
    ├── lib/
    ├── pubspec.yaml
    └── ...
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Flutter](https://flutter.dev/) SDK
- Access to the SQL Server database (ask the team for credentials)

---

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo
```

---

### 2. Backend Setup

```bash
cd backend
npm install
npx prisma generate
```

Create your `.env` file from the example:

```bash
cp .env.example .env
```

Then open `.env` and fill in the real values:

```
DB_SERVER=your_server_ip
DB_PORT=your_port
DB_USER=your_username
DB_PASSWORD=your_password
DB_NAME=your_database_name
DATABASE_URL="sqlserver://your_server_ip:your_port;database=your_database_name;user=your_username;password=your_password;trustServerCertificate=true;encrypt=false"
```

Run the backend:

```bash
node server.js
```

You should see:
```
Server running on port 3000
```

Verify it's working:
```bash
curl http://localhost:3000/
# expected: {"status":"ok"}
```

---

### 3. Flutter Setup

```bash
cd flutter_project
flutter pub get
flutter run
```

---

## Environment Variables

Never commit `.env` — it contains sensitive credentials. Use `.env.example` as a reference.

| Variable | Description |
|---|---|
| `DB_SERVER` | SQL Server IP address |
| `DB_PORT` | SQL Server port |
| `DB_USER` | Database username |
| `DB_PASSWORD` | Database password |
| `DB_NAME` | Database name |
| `DATABASE_URL` | Full Prisma connection string |

---

## Notes

- `node_modules/` and `.env` are gitignored — never push them
- After cloning, always run `npm install` and `npx prisma generate` before starting the backend
- After cloning, always run `flutter pub get` before running the Flutter app
- Contact the team to get the actual `.env` credentials
