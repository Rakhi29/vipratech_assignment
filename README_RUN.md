# Run Instructions (development)

This project is intentionally minimal to be easy to inspect.

Prerequisites:
- Python 3.10+
- pip
- PostgreSQL (or change DATABASES in settings to sqlite3 for quick test)

Quick sqlite dev run:
1. cd project_root
2. python -m venv venv
3. source venv/bin/activate
4. pip install -r requirements.txt
5. cp .env.example .env
6. (optional) edit .env values (STRIPE keys)
7. python manage.py migrate
8. python manage.py loaddata products_seed.json
9. python manage.py runserver

Visit http://127.0.0.1:8000/ to see the page.

Stripe:
- Use your Stripe test keys in .env
- For webhooks in dev, use `stripe listen` or configure webhook forwarding.
