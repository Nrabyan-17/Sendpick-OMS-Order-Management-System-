# SendPick - Order Management System (OMS)

## 🚀 Deskripsi Proyek
SendPick OMS adalah aplikasi **Order Management System** untuk kebutuhan logistik. Proyek ini dirancang sebagai aplikasi berbasis SaaS (Software as a Service) dengan arsitektur **multi-tenant** sehingga dapat digunakan oleh banyak perusahaan logistik sekaligus dengan data yang terisolasi.

Teknologi utama yang digunakan:
- **Backend**: Laravel (PHP)
- **Frontend**: React.js (JavaScript)
- **Database**: PostgreSQL (schema per tenant)

---

## 📂 Struktur Repository
Repository ini akan dibagi menjadi 2 folder utama:
- `/backend` → source code Laravel
- `/frontend` → source code React
- `/docs` → dokumentasi (ERD, API spec, mockup)

---

## 🛠️ Setup Repository & Architecture
Langkah awal:
1. Inisialisasi repo Git (`git init`).
2. Tambahkan struktur dasar folder backend & frontend.
3. Siapkan Dockerfile atau environment setup (opsional).
4. Pastikan ada file `.env.example` untuk konfigurasi.

Arsitektur yang digunakan:
- **Landlord App** → pendaftaran tenant, billing, admin pusat.
- **Tenant App** → aplikasi logistik masing-masing tenant.

---

## 🗄️ Database Schema Design
> (Tugas yang perlu kamu kerjakan di tahap ini)

- Buat **ERD (Entity Relationship Diagram)** untuk schema landlord & tenant.
- Schema **public (landlord)** minimal punya:
  - `tenants` (id, name, domain, status)
  - `users` (id, name, email, password)
  - `subscriptions`, `plans`, `invoices`
- Schema **tenant_xxx** minimal punya:
  - `orders` (origin, destination, status, consignee_id)
  - `customers` (name, address)
  - `drivers` (name, vehicle_id)
  - `vehicles` (license_plate, type)

Output: file ERD + migration awal di folder `/backend/database/migrations`.

---

## ⚙️ Backend Skeleton & API Setup
> (Tugas yang perlu kamu kerjakan di tahap ini)

- Inisialisasi proyek Laravel (`laravel new backend`).
- Konfigurasi PostgreSQL dan multi-tenancy (gunakan `spatie/laravel-multitenancy`).
- Buat **auth system** menggunakan Laravel Sanctum.
- Buat **API routes** dasar:
  - `POST /login` → login user
  - `GET /orders` → ambil list order (tenant-based)
  - `POST /orders` → buat order baru
- Gunakan **API Resource** untuk response JSON yang konsisten.

---

## 🔗 API Documentation
API akan didokumentasikan di `/docs/api.md` menggunakan format OpenAPI/Swagger.

---

## 📅 Timeline (Tahap Awal)
- Week 1–2: Setup repo & architecture
- Week 2–3: Database schema design
- Week 3–4: Backend skeleton & API setup
