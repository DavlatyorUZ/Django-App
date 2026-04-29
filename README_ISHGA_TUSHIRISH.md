# Django loyihani lokalda ishga tushirish

## 1) Virtual muhit

```bash
cd django-loyiha
python3 -m venv venv
source venv/bin/activate
```

## 2) Kutubxonalarni o‘rnatish

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## 3) Bazani tayyorlash

Loyiha SQLite ishlatadi. PostgreSQL kerak emas.

```bash
python manage.py migrate
```

## 4) Admin yaratish

```bash
python manage.py createsuperuser
```

## 5) Static fayllarni yig‘ish

```bash
python manage.py collectstatic --noinput
```

## 6) Serverni ishga tushirish

```bash
python manage.py runserver
```

Sayt: http://127.0.0.1:8000/
Admin: http://127.0.0.1:8000/admin/

## Muhim tuzatishlar

- PostgreSQL o‘rniga SQLite sozlandi.
- `.env` yaratildi.
- `djangorestframework` requirements ichiga qo‘shildi.
- `qidiruv/` URL qo‘shildi. Aks holda bosh sahifa `NoReverseMatch` berardi.
- CSS/static sozlamalari to‘g‘rilandi.

## API dokumentatsiya va CORS

Qo'shilgan paketlar:

```bash
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Swagger UI:

```text
http://127.0.0.1:8000/api/docs/
```

OpenAPI schema:

```text
http://127.0.0.1:8000/api/schema/
```

ReDoc:

```text
http://127.0.0.1:8000/api/redoc/
```

CORS development originlari `saytim/settings.py` ichida berilgan:

- `http://localhost:3000` — React
- `http://localhost:8080` — Vue
- `http://localhost:4200` — Angular

Agar lokal developmentda vaqtincha hamma frontend originlariga ruxsat kerak bo'lsa, `.env` ichiga qo'shing:

```env
CORS_ALLOW_ALL_ORIGINS=True
```

Productionda buni `False` qoldiring va faqat real domenlarni `CORS_ALLOWED_ORIGINS` ichida saqlang.
