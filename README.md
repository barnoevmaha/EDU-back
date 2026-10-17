# EduCenter — Backend

API for a small learning-centre app with three roles: **student**, **teacher**, **admin**.
Attendance, homework with submissions, timetable, a news feed with comments, and a leaderboard
where students earn coins. Interface language of the whole app is Uzbek.

Frontend: [EDU-front](https://github.com/barnoevmaha/EDU-front).

## Stack

FastAPI, Pydantic v2, plain `sqlite3` (8 tables, schema in `app/db.py`) — deliberately no ORM,
to keep the whole backend readable in one sitting.

## API

| Area | Routes |
|---|---|
| Auth | `POST /api/auth/login` |
| Users / admin | list, get, set status, delete, delete group, add student, give coins, upload avatar, login log, stats |
| Homework | list, create, delete, `POST /{id}/submit` |
| Posts | list, create, delete, `POST /{id}/comments` |
| Attendance | list, mark, `GET /student/{id}` |
| Schedule | list, create, delete |
| Leaderboard | `GET /api/leaderboard` |

Interactive docs at `/docs`.

## Run

```bash
pip install -r requirements.txt
python run.py            # http://127.0.0.1:8000
```

Or `docker build -t edu-back . && docker run -p 8000:8000 edu-back`.
