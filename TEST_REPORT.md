# Test hisoboti

## Qilingan ishlar

- `views.py` qayta tartiblandi va takrorlangan API viewlar olib tashlandi.
- DRF `PostViewSet` qo'shildi: list/create/retrieve/update/delete.
- Token auth endpointlari tayyorlandi:
  - `POST /api/kirish/`
  - `POST /api/chiqish/`
  - `POST /api/royxatdan-otish/`
- CRUD API endpointlari qo'shildi:
  - `GET/POST /api/postlar/`
  - `GET/PUT/PATCH/DELETE /api/postlar/{id}/`
  - `GET /api/postlar/ommabop/`
  - `GET /api/postlar/mening_postlarim/`
- Function-based API endpointlari alohida saqlandi:
  - `/api/postlar-fbv/`
- `FaqatMuallifOzgartiradi` permission qo'shildi.
- `django-filter` requirements va settings ichiga qo'shildi.
- `like_post` URL xatosi tuzatildi.
- `post_izoh` noto'g'ri template chaqirish xatosi tuzatildi.
- Post tahrirlash formasiga rasm yuklash uchun `enctype="multipart/form-data"` qo'shildi.
- Serializerda `muallif` read-only qilindi, chunki muallif avtomatik `request.user`dan olinadi.

## Muhitda bajarilgan tekshiruv

Quyidagi fayllar Python syntax compile orqali tekshirildi:

```bash
python -m py_compile blog/views.py blog/urls.py blog/serializers.py blog/models.py blog/forms.py blog/permissions.py saytim/settings.py saytim/urls.py
```

Natija: syntax xatolik topilmadi.

## Lokal kompyuterda yakuniy tekshirish buyruqlari

```bash
cd django-loyiha
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py check
python manage.py runserver
```

API sinovi:

```bash
curl http://127.0.0.1:8000/api/postlar/
```
