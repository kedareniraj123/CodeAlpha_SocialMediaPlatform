# CodeAlpha_SocialMediaPlatform

A mini social media app built with Django, created for the CodeAlpha Full Stack Development internship (Task 2).

## Features

- **User profiles** — bio, avatar, follower/following counts, editable profile
- **Posts** — create text posts with optional image, shown newest-first
- **Comments** — comment on any post
- **Likes** — like/unlike posts (heart toggle)
- **Follow system** — follow/unfollow users; personalized feed shows only posts from people you follow (+ your own)
- **Explore page** — see all posts to discover new people to follow
- **Admin panel** — manage users, posts, comments, likes, follows at `/admin/`

## Tech Stack

- Backend: Django 5/6 (Python)
- Frontend: Django templates + plain HTML/CSS
- Database: SQLite (default)

## Setup

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

pip install -r requirements.txt
python manage.py migrate

# optional: seed 3 demo users (password: password123) with sample posts/follows
python manage.py seed_data

python manage.py createsuperuser
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` for the app and `http://127.0.0.1:8000/admin/` for the admin panel.

## Project Structure

```
CodeAlpha_SocialMediaPlatform/
├── socialmedia/         # Project settings, root URLs
├── social/              # Main app
│   ├── models.py        # Profile, Post, Comment, Like, Follow
│   ├── signals.py       # Auto-creates a Profile on user signup
│   ├── views.py         # Feed, explore, post detail, likes, follow, profile
│   ├── forms.py         # Post, comment, profile, signup forms
│   ├── templates/
│   └── management/commands/seed_data.py
├── static/css/style.css
├── requirements.txt
└── manage.py
```

## Notes / Next Steps

- The feed only shows posts from people you follow — use Explore to find and follow users.
- Add pagination once post volume grows.
- Consider WebSockets (Django Channels) for real-time notifications as a bonus feature.
- For the CodeAlpha submission: push this repo as `CodeAlpha_SocialMediaPlatform` on GitHub, record a short walkthrough video, and post it on LinkedIn tagging @CodeAlpha.
Author : Niraj Kedare
